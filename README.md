# ATP (Auto Test Platform)

ATP is an automated testing platform designed to streamline and manage testing workflows. It is built with Java, Spring Boot, Gradle, GraphQL, Netflix DGS and supports integration with SQL databases.

**Note:** This project is currently under active development.

## Features

- Automated test execution and management
- Modular backend with Spring Boot
- GraphQL API powered by Netflix DGS framework
- Dockerized deployment support
- Integration with MySQL and other databases
- Configurable via YAML files

## Project Structure

- `atp-server/` - Main backend service (Java, Spring Boot)
- `docker-scripts/` - Docker Compose files and utility scripts
- `db/` - Database initialization scripts
- `config/` - Configuration files
- `logs/` - Log output directory

## Getting Started

### Prerequisites

- JDK 8+
- Docker & Docker Compose
- Gradle

### Build and Run

1. Clone the repository:
   ```sh
   git clone git@github.com:ztom99/atp-backend.git
   cd atp-backend
2. Build the project:
   ```sh
    ./gradlew build
3. Start the database and dependencies:
    ```sh
   cd docker-scripts/atp
   docker-compose -f mysql.yml up -d
   cd ../../
4. Run the backend service:
    ```sh
   ./gradlew :atp-server:bootRun

### Docker Image
1. Build the docker image:
    ```sh
    ./gradlew :atp-server:dockerBuildImage
    docker run -p 8080:8080 com.bcs.atp/atp-server:latest

## Configuration
1. Application configs: atp-server/src/main/resources/application-*.yml
2. Database scripts: docker-scripts/atp/mysql/

