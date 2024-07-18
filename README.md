# How to Run PySpark on Your Local Machine Using Docker Desktop

## Pre-requisites:
- **Machine:** Mac Operating System
- **Software:** Docker Desktop installed

## Step 1: Pull the Docker Image for PySpark

1. Open Terminal on your Mac.
2. Pull the Docker image by running the following command:
    ```bash
    docker pull quay.io/jupyter/pyspark-notebook
    ```

## Step 2: Prepare Your Working Directory

1. **Optional:** If you want to save files created inside the container to your local machine, create a working directory:
    - Open Terminal and run:
      ```bash
      mkdir /Users/<yourName>/<YourWorkingDirectory>/
      cd /Users/<yourName>/<YourWorkingDirectory>/
      ```

2. Run the Docker container with the following command:
    ```bash
    docker run -it --rm -p 10000:8888 -v "${PWD}":/home/jovyan/work quay.io/jupyter/pyspark-notebook
    ```

## Step 3: Access Jupyter Notebook

1. Open your web browser.
2. Go to [http://localhost:10000](http://localhost:10000).

## Step 4: (Optional) Run Jupyter Notebook in Visual Studio Code

1. Create a new `.ipynb` file in VS Code (as you normally would).
2. Select the kernel by following these steps:
    - Click on the kernel selection in the top right.
    - Choose **"Existing Jupyter Server"**.
    - Enter the host: `http://localhost:10000`.
    - For the password, check the logs from the Terminal where you ran the Docker command. Look for the token and use it as the password.

That's it! You are now ready to use PySpark on your local machine with Docker.
