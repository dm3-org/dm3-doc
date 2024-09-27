# Setting up the dm3 backend locally

## Getting Started

This guide will walk you through the steps to set up the backend for the DM3 service. The backend setup involves configuring environment variables, setting up a Redis cache, a PostgreSQL database, and running the backend service in a Docker container.

## Step-by-step guide to set up a DM3 backend service

Follow the steps below to set up your DM3 backend service:

### Step 1: Prepare your directory

1. **Create a new directory:** Start by creating a new directory on your machine where you will store the backend configuration files. For example, create a directory named `dm3-backend`.

```bash
mkdir dm3-backend
cd dm3-backend
```

2. **Download the docker compose file:** Download the <mark style="color:blue;">docker-compose.yml</mark> file into this newly created directory. This file defines the services required to run the backend, including:
   * `backend`: The main backend service for `dm3`.
   * `db`: A Redis service for caching.
   * `dm3-storage`: A PostgreSQL database service for storing data.

### Step 2: Create the `.env` file

create a `.env` file in the same directory (`dm3-backend`). This file will contain the environment variables needed to configure the backend services.

1. **Create the `.env` File:** In the `dm3-backend` directory, create a `.env` file.

```bash
touch .env
```

2. **Copy the below content and paste it into the .env file:**

```bash
PERSISTENCE_DIRECTORY=/path/to/your/persistence/directory
DATABASE_URL=postgresql://prisma:prisma@dm3-storage:5432/dm3
RPC=your_rpc_url
```

Replace the placeholder values with your actual keys and URLs:

* **PERSISTENCE\_DIRECTORY:** Path to a local directory on your machine where Redis and PostgreSQL data will be persisted.
* **DATABASE\_URL:** This specifies the connection string for the PostgreSQL database. It is pre-configured to use the `dm3-storage` service defined in the Docker Compose file.
* **RPC:** Replace `your_rpc_url` with the URL for your Ethereum RPC provider (e.g., Infura or Alchemy).

### Step 3: Start the backend services

Once you have the `docker-compose.yml` and `.env` files in place in the `dm3-backend` directory, you can start the backend services.

1. **Open a Terminal:** Open a terminal in the `dm3-backend` directory.
2.  **Run the Docker Compose Command:** Execute the following command to start all the backend services:

    ```bash
    docker compose --env-file .env up -d
    ```

    \
    This command will start the backend services defined in the `docker-compose.yml` file, including the `backend` service, `db` (Redis), and `dm3-storage` (PostgreSQL). The `-d` flag runs the services in detached mode.

### Step 4 : **Verify the service:**&#x20;

Open a web browser and navigate to `<yourUrl>:8081/hello` to see a friendly response from your newly set-up backend service. Replace `<yourUrl>` with the URL you provided earlier.

### Step 5: Use the backend URL in your frontend application

After starting the backend service, you need to configure your frontend application to communicate with the backend. The backend service is exposed on port `8001`.

**If You Are Running the Backend Locally**

* The URL for connecting to the backend will likely be `http://localhost:8001`.

Ensure your frontend application is properly configured to use this URL for any API requests or backend interactions.

**Update Environment Variables in Your Frontend Application**

In your React application, you should set environment variables to point to the backend URL. This can be done by adding or updating the following lines in your `.env` file:

```bash
REACT_APP_BACKEND=http://localhost:8001
REACT_APP_PROFILE_BASE_URL=http://localhost:8001
```

Make sure to restart your React application after updating the `.env` file for the changes to take effect.
