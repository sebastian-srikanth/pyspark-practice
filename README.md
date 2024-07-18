# How to run PySpark in local machine using docker desktop

# 1. First Pull the docker image replated to pyspark
* Pull the image "quay.io/jupyter/pyspark-notebook" by running below command


**NOTE**: If you need to save the files in the local machine created from container then goto your workspace.

* for example: Create your working Directory `/Users/<yourName>/<YourWorkingDirectory>/`
* goto your working directory `cd /Users/<yourName>/<YourWorkingDirectory>/`
* Finally run the below command
```bash
docker run -it --rm -p 10000:8888 -v "${PWD}":/home/jovyan/work quay.io/jupyter/pyspark-notebook
```

# 2. Open the below link in a browser
http://localhost:10000

# 3. Run Jupyter notebook in VS Code ( Optional )
* Create a new ipynb file ( as we normally create )
* Select Kernel
    * Existing Jupyter server
    * Enter host: http://localhost:10000
    * Enter password: Check the logs when you ran docker pull command, paste the token as password.
