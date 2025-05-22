# Assignment 2: Use Azure Storage in Your Web App 📦🌐

In this assignment, you'll enhance your Python web app by using Azure Blob Storage to serve static files (e.g., images or downloadable files).

## ✅ Step 1: Create an Azure Storage Account

Azure Storage Account is a service that provides a unique namespace in Azure for storing your data. It allows you to store and retrieve large amounts of unstructured data, such as text or binary data.

1. In the Azure portal, search for **Storage accounts** and click **Create**.
2. Use the same resource group as before.
3. Choose a unique name (e.g., `stclouddevopslab<yourname>`). Be sure it is not exceeding 24 characters and contains only lowercase letters or numbers.
4. Select the **Region** where your app service is located (e.g., `West Europe`).
5. Set **Primary service** to `Azure Blob Storage or Azure Data Lake Storage Gen 2`.
6. Select the **Redundancy** as `Locally redundant storage (LRS)`.
   - This is the most cost-effective option for development and testing purposes.
   - For production, you may want to consider other redundancy options based on your needs.
7. [Optional] Explore the rest of the options and leave them as default. 
8. Click **Review + Create** and then **Create**.

    > ⌛ Wait for the deployment to complete. This may take a few minutes.
    > [Optionally] Learn more about [Azure Storage](https://learn.microsoft.com/en-us/azure/storage/common/storage-introduction).

## ✅ Step 2: Create a Blob Container & Upload Static Files

A Blob Container is a logical grouping of blobs (files) in Azure Storage. You can think of it as a folder in a file system.

1. In the storage account, go to **Configuration** from the left menu.
2. Enable **Allow Blob anonymous access** and click **Save**.
3. From the left menu, go to **Containers**.
4. Click **➕ Container** to create a new container.
5. Name it `hello-cloud-devops-app-contents` (or any name you prefer).
6. Set public access level to **Blob (anonymous read access for blobs only)**.
7. Upload any static files you want to serve (e.g., images, PDFs, etc.).

## ✅ Step 3: Modify Flask App to Use Blob URLs

Update your HTML templates to reference files from the Azure Blob Storage.

1. Open the `templates/index.html` file in your web app.
2. Retrieve the URL of the blob you uploaded.
   - In the Azure portal, navigate to your storage account and select the container you created.
   - Click on the blob you uploaded to get its URL.
3. Add the following code to display an image fetched from Azure Blob Storage:
   ```html
   <img src="<BLOB_URL>" alt="Image from Azure Blob Storage">
   ```
   The `<BLOB_URL>` should be replaced with the URL of the blob you uploaded. The URL format is:
   ```
    https://<STORAGE_ACCOUNT_NAME>.blob.core.windows.net/<CONTAINER_NAME>/<BLOB_NAME>
    ```
4. You can also add links to downloadable files in a similar way:
   ```html
   <a href="<BLOB_URL>" download>Download File</a>
   ```
5. Commit your changes and watch the GitHub Actions workflow run to deploy the updated app.
6. [Optional] If you're editing the code in your local environment, you can commit and push the changes to your forked repository by running:
   ```bash
   git add .
   git commit -m "Add Azure Blob Storage integration"
   git push origin main
   ```
7. Navigate to your web app URL to see the changes in action.

Congratulations! You've successfully integrated Azure Blob Storage into your web app. Now you can serve static files directly from Azure Storage. 🏆🏆

You’re now ready to proceed to [Assignment 3: Use Azure SQL Database in Your Web App](assignment-3-use-azure-sql-database.md) 🎯