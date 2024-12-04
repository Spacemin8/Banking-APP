# Bank App

A simple responsive banking application built with Next.js, React, and Material-UI, with a backend powered by Prisma and PostgreSQL. This application allows users to view account balances, make deposits, withdraw funds, and track transaction history.

## Features

- View and update account balances
- Make deposits, withdrawals, and transfers
- View transaction history
- Responsive design using Material-UI

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed
- [Node.js](https://nodejs.org/) (v14 or above) installed
- [Yarn](https://yarnpkg.com/) or [npm](https://www.npmjs.com/) for package management

## Setup Instructions

Follow the steps below to set up and run the project locally.

### 1. Set up PostgreSQL with Docker

First, you need to run the PostgreSQL container using Docker. This will set up a local PostgreSQL database for the application.

#### Step 1: Clone the repository

```bash
git clone https://github.com/Shoaib-Naseer/banking-app.git
cd bank-app
```

#### Step 2: Run Docker Compose
In the root of the project, run Docker Compose to start the PostgreSQL container.

```bash
docker-compose up -d
```
This will start PostgreSQL and any other services defined in the docker-compose.yml file. The database should now be running locally.

#### Step 3: Set up environment variables
Create a .env file in the root of the project. This file will store your environment variables for database connectivity and other configurations.

Example .env file:

```bash
DATABASE_URL=postgresql://myuser:mypassword@localhost:5432/mydatabase?schema=public
NEXT_PUBLIC_API_URL=http://localhost:3000/api
```
Make sure to replace username and password with your PostgreSQL credentials. You can modify these settings based on your Docker setup.

### Step 4. Install Dependencies
Install the project dependencies using either Yarn or npm.

Using Yarn:
```bash
yarn install
```
Using npm:
```bash
npm install
```
### Step 5. Set up Prisma and migrate the database
Run the following command to apply the database migrations. This will create the necessary tables and schema in your PostgreSQL database.

```bash
npx prisma migrate dev --name init
```
This command will generate the database schema and apply the migration to your PostgreSQL database.

### Step 6. Run the Application
You can now run the development server with:

Using Yarn:
```bash
yarn dev
```
Using npm:
```bash
npm run dev
```
This will start the application at http://localhost:3000.