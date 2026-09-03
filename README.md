# Tasty

Tasty application, responsible for exposing the BFF endpoints and communicating with the authentication and restaurant services.

## Requirements

Install the following software:

- Java JDK 21
- Git
- PostgreSQL 17 (or Docker Desktop with Docker Compose)
- An IDE such as IntelliJ IDEA or Eclipse (optional)

The project uses the Gradle Wrapper, so it is not necessary to install Gradle globally.

## Project structure

```text
common       Shared classes and configurations
contract     Controllers, security and API contracts
impl         Business rules and application services
integration  Integrations with external services
```

We are using the `docker-compose.yml` from the authentication service, start PostgreSQL with:

```bash
docker compose up
```

## Configuration of dependent services

The BFF depends on the following services in the development environment:

| Service | Default URL | Context Path |
|---|---|---|
| Tasty API Service | `http://localhost:3000` | `/tasty-api-service` |
| Tasty Auth Service | `http://localhost:8085` | `/tasty-auth-service` |
| Tasty App Bff | `http://localhost:8081` | `/tasty-app-bff` |
| ViaCEP | `https://viacep.com.br/ws` |

> The authentication service must be running before using protected BFF endpoints.

## Clone the project

```bash
git clone <URL_DO_REPOSITORIO>
```

## Configure Java

Check the installed Java version:

```bash
java -version
```

The project should run with Java 21. If multiple Java versions are installed, configure `JAVA_HOME` to point to the JDK 21 installation.

### Windows PowerShell example

```powershell
$env:JAVA_HOME="C:\Program Files\Java\jdk-21"
$env:Path="$env:JAVA_HOME\bin;$env:Path"
java -version
```

## Install dependencies and build

### Windows

Run from the project root:

```powershell
.\gradlew.bat clean build
```

### Linux/macOS

```bash
chmod +x ./gradlew
./gradlew clean build
```

The Gradle Wrapper downloads the required Gradle version automatically on the first execution.

## Run using the IDE

1. Import the project as a Gradle project.
2. Configure the JDK as Java 21.
3. Set the active profile to `dev`.
4. Run the main Spring Boot class.

## Test the API

After starting the application, authenticate through the authentication service and copy the returned JWT.

Send the token in the BFF request:

```http
GET http://localhost:8081/tasty-app-bff/v1/restaurante/dashboard
Authorization: Bearer SEU_TOKEN_JWT
```

The BFF extracts the user ID from the token and calls the restaurant service.

## Troubleshooting

### `gradle` is not recognized

Use the project wrapper instead of the global Gradle command:

```powershell
.\gradlew.bat tasks
```

### `Connection refused`

Check whether the dependent service is running and whether its URL and port are correct in `application-dev.yml`.

### `404 Not Found` when calling another service

Check the service context path. For example, if the restaurant service uses `/tasty-api-service`, the Feign URL must include that context:

```yaml
url: http://localhost:3000/tasty-api-service
```

### PostgreSQL connection error

Confirm that PostgreSQL is running, that the database `tasty` exists, and that the username/password in `application-dev.yml` are correct.

## Useful commands

```powershell
# Show Gradle version
.\gradlew.bat --version

# List tasks
.\gradlew.bat tasks

# Clean build
.\gradlew.bat clean build

# Run tests
.\gradlew.bat test

# Stop a process using a port
netstat -ano | findstr :8081
taskkill /PID <PID> /F
```
