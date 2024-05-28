
# EZNap 💤

EZNap is a demo backend API microservices project designed to create an account and make reservations for hotels, rooms, or other services. This project uses NestJS and MongoDB, and it is containerized using Docker.

## Tech Stack

**Client:** N/A (Backend Project)

**Server:** Node.js, NestJS

**Database:** MongoDB

**Containerization:** Docker, Docker Compose

## Table of Contents

- [Installation](#installation)
- [Running the Project](#running-the-project)
  - [With Docker](#with-docker)

## Installation

To set up this project locally, follow these steps:

1. **Clone the repository:**
    ```sh
    git clone https://github.com/ASonneP/eznap.git
    cd eznap
    ```

2. **Install dependencies:**
    ```sh
    npm install
    ```

3. **Set up environment variables:**
    Copy the `.env.template` to `.env` and fill in the necessary configuration.
    ```sh
    cp .env.template .env
    ```

## Running the Project

### With Docker

Docker simplifies running the application by containerizing it. Ensure you have Docker and Docker Compose installed on your machine.

1. **Build and run the containers:**
    ```sh
    docker-compose up --build
    ```

2. **Access the application:**
    The API should be running on `http://localhost:3000` (or the port you have configured).

