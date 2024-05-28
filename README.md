
# EZNap 💤

EZNap is a demonstration backend API microservices project aimed at facilitating account creation and hotel, room, or service reservations. Built with NestJS and MongoDB, this project is fully containerized using Docker.

## Tech Stack

**Client:** N/A (Backend Project)

**Server:** Node.js, NestJS

**Database:** MongoDB

**Containerization:** Docker, Docker Compose

## Table of Contents

- [Installation](#installation)
- [Running the Project](#running-the-project)
  - [With Docker](#with-docker)
- [API Reference](#api-reference)
  - [Register](#register)
  - [Login](#login)
  - [Create Reservation Payment](#create-reservation-payment)

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



## API Reference

### Register

```http
  POST http://localhost:3001/users
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `email` | `string` | **Required**. Your email |
| `password` | `string` | **Required**. Your password |

### Login

```http
  POST http://localhost:3001/auth/login
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `email` | `string` | **Required**. Your email |
| `password` | `string` | **Required**. Your password |

### Create Reservation Payment
**Note: This endpoint requires the user to be signed in.**
```http
  POST http://localhost:3000/reservations
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `user_id`              | `string` | **Required**. Id of the user                |
| `item_id`              | `string` | **Required**. Id of the item to reserve     |
| `startDate`            | `string` | **Required**. Start date of the reservation (MM/DD/YYYY) |
| `endDate`              | `string` | **Required**. End date of the reservation (MM/DD/YYYY)   |
| `placeId`              | `string` | **Required**. Id of the place               |
| `invoiceId`            | `string` | **Required**. Id of the invoice             |
| `charge`               | `object` | **Required**. Charge details                |
| `charge.amount`        | `number` | **Required**. Amount to be charged          |
| `charge.card`          | `object` | **Required**. Card details                  |
| `charge.card.cvc`      | `string` | **Required**. Card CVC                      |
| `charge.card.exp_month`| `number` | **Required**. Card expiration month         |
| `charge.card.exp_year` | `number` | **Required**. Card expiration year          |
| `charge.card.number`   | `string` | **Required**. Card number                   |



