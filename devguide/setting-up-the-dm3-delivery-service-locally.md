# Setting up the dm3 delivery service locally

## Getting Started

This guide will walk you through the process of setting up a DM3 delivery service locally. The setup involves generating configuration files, saving keys, publishing a profile, and running the service using Docker.

You have the option to use the [<mark style="color:blue;">dm3-ds-setup-helper</mark>](https://dm3-org.github.io/dm3-ds-setup-helper/) tool, which is a web app designed to simplify the setup process. The tool provides a streamlined way to generate configuration files, publish the delivery service profile to the Ethereum blockchain, and download necessary files for Docker setup. Most of the steps outlined in this guide can be completed directly through the tool, providing a user-friendly interface and prompts to make the setup process as smooth as possible.

## Step-by-step guide to set up a DM3 delivery service

Follow the steps below to set up your DM3 delivery service:

### Step 1: Create config and profile

The first step is to generate the configuration and profile files for your delivery service. This can be done using the [dm3-ds-setup-helper](https://dm3-org.github.io/dm3-ds-setup-helper/) tool.

1. **Connect your account:** Start by connecting the Ethereum account that the delivery service will use. This account should have control over the ENS domain you'll be using.\

2. **Enter the required information:**
   * **ENS:** Provide the ENS domain that your delivery service will use, e.g., `myPersonalDeliveryService.eth`.
   * **URL:** Enter the URL where your delivery service will be hosted, e.g., `https://my-personal-delivery-service.com`. You can also use a localhost URL for local testing, e.g., `http://localhost:8083`.
   * **RPC:** Specify the RPC URL that your delivery service will use to interact with the Ethereum blockchain, e.g., `https://mainnet.infura.io/v3/YOUR_INFURA_PROJECT_ID`. You can also add this later to the `dm3-ds.env` file.\

3. **Generate profile and `.env` file:** Using the [<mark style="color:blue;">dm3-ds-setup-helper</mark>](https://dm3-org.github.io/dm3-ds-setup-helper/) web app, generate the profile and the `.env` file. This can be done offline.

### Step 2: Store `dm3-ds.env` and `config.yml`

Once the profile and `.env` file are generated:

1. **Download the files:** Download the `dm3-ds.env` and `config.yml` files from the setup helper tool.\

2. **Store the files securely:** Ensure that both files are stored securely on your local machine, as they contain sensitive information necessary for setting up the delivery service.

### Step 3: Publish profile

Now that you have your configuration files, you'll need to publish the profile associated with your delivery service on the ENS domain.

1. **Connect the ENS controlling account:** Connect the Ethereum account that controls the ENS domain to the setup helper tool.\

2. **Ensure ENS and profile information is correct:**
   * **ENS:** If the ENS name field is not auto-populated, copy the value of `ENS_DOMAIN` from the `dm3-ds.env` file and paste it into the input field.
   * **Profile:** If the profile data is not auto-populated, copy the `PROFILE` value from the `dm3-ds.env` file (as a JSON object) and paste it into the input field.\

3. **Publish profile:** Once the ENS and profile data are set, publish the profile using the setup helper tool. This step requires an internet connection as it executes a transaction on the Ethereum blockchain.\

4.  **Verify the record on ENS:**

    * After publishing, you can verify that the profile record has been added to your ENS domain by visiting the [ENS Manager App](https://app.ens.domains/).
    * Search for your ENS domain in the app.
    * Click on **Records** and look for a text record with the key `network.dm3.deliveryService`.
    * The record's value should be in the following format:

    <pre class="language-bash"><code class="lang-bash"><strong>data:application/json,{"publicEncryptionKey":"publicEncryptionKey",
    </strong><strong>"publicSigningKey":"publicSigningKey",
    </strong><strong>"url":"&#x3C;your_delivery_service_url>"
    </strong></code></pre>

    \
    Ensure that the `publicEncryptionKey`, `publicSigningKey`, and `url` match the values you intended to publish. If everything is correct, your delivery service profile has been successfully published to the ENS domain.

### Step 4: Dockerize and run the delivery service

Now that your profile is published, you can set up the delivery service using Docker.

1. **Download the docker compose file:** Download the <mark style="color:blue;">docker-compose.yml</mark> file and save it locally.\

2. **Prepare the directory:** Create a directory on the machine where you plan to run the delivery service (e.g., a web server). Move the `docker-compose.yml`, `dm3-ds.env`, and `config.yml` files into this directory.\

3. **Run the service:**
   * Open a terminal in the directory containing the files.
   * Execute the following command to start the delivery service:

```bash
docker compose --env-file dm3-ds.env up -d
```

This command will use the `docker-compose.yml` file to set up the required containers for the dm3 delivery service.

4. **Verify the service:** Open a web browser and navigate to `<yourUrl>:8083/hello` to see a friendly response from your newly set-up delivery service. Replace `<yourUrl>` with the URL you provided earlier.

### Step 5: Use the delivery service URL in your frontend application

Update the `.env` file in your frontend application to set the delivery service ENS domain:

```bash
REACT_APP_DEFAULT_DELIVERY_SERVICE=<your_delivery_service_ens>
```

Replace `<your_delivery_service_ens>` with your delivery service's ENS domain.



