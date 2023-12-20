# Azure Blob Uploader

## Overview

clouduploader is a Bash script designed to securely upload files to Azure Blob Storage. It features a progress bar for visualization, file encryption using GPG, and the generation of shareable links for the uploaded files.

## Prerequisites

Before using this tool, ensure that you have the following prerequisites installed:

1. **Azure CLI:** Install the Azure Command-Line Interface by following the instructions [here](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli).

2. **pv (Pipe Viewer):** Install the `pv` utility for progress bar visualization. On Debian-based systems, you can use the following command:
    ```bash
    sudo apt-get install pv
    ```

3. **GPG (GNU Privacy Guard):** Install GPG for file encryption. Refer to the GPG documentation for installation instructions: [GPG Installation](https://gnupg.org/download/index.html).

## Usage

1. Clone this repository or download the `clouduploader.sh` script.

2. Open the script in a text editor and update the Azure storage account details:

    ```bash
    AZURE_ACCOUNT_NAME="your_storage_account_name"
    AZURE_CONTAINER_NAME="your_container_name"
    AZURE_ACCOUNT_KEY="your_account_key"
    ```

3. Run the script with the desired files to upload:

    ```bash
    ./clouduploader.sh <file-path1> [file-path2] [file-path3] ...
    ```

## Configuration

Make sure to update the Azure storage account details in the script:

- **`AZURE_ACCOUNT_NAME`:** Your Azure Storage account name.
- **`AZURE_CONTAINER_NAME`:** The name of the Azure Blob Storage container.
- **`AZURE_ACCOUNT_KEY`:** Your Azure Storage account key.

## File Actions

- **Overwrite (o):** Overwrite the existing file in Azure Blob Storage.
- **Skip (s):** Skip the current file and continue with the next one.
- **Rename (r):** Rename the file before uploading.

## Encryption

Files are encrypted before uploading using GPG with the AES256 symmetric encryption algorithm.

## Feedback

After each upload, the script provides feedback on the success or failure of the operation along with a shareable link.

## Cleanup

The encrypted file is removed after a successful upload.

## Troubleshooting

- **File Not Found Error:** If you encounter a "File not found" error, double-check the file paths provided as arguments.

- **Azure CLI Error:** Ensure that the Azure CLI is installed and configured correctly with the required permissions.

- **pv Installation Error:** If `pv` is not installed, follow the provided installation instructions.

- **GPG Encryption Error:** If GPG encounters issues during encryption, verify that GPG is installed and the file is accessible.

- **Azure Blob Storage Access Error:** Check that the provided Azure storage account details are accurate and that you have the necessary permissions to upload to the specified container.

## Disclaimer

This script is provided as-is without any warranties. Use it at your own risk and ensure that you have the necessary permissions to interact with Azure Blob Storage.

