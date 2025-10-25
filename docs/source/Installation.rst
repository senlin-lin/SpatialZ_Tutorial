Installation
============

This document provides detailed instructions for installing and setting up the SpatialZ project.
Follow the steps below to configure your environment and install dependencies.

Step 1: Create a new virtual environment called spatialz with Python 3.9.19
----------------------------------------------------------------------------

.. code-block:: bash

    conda create -n spatialz python=3.9.19 -y

Step 2: Activate the spatialz environment
------------------------------------------

.. code-block:: bash

    conda activate spatialz

Step 3: Install PyTorch with CUDA 11.7 support
------------------------------------------------

.. code-block:: bash

    pip install torch==1.13.0+cu117 -f https://download.pytorch.org/whl/cu117/torch_stable.html

Step 4: Clone the SpatialZ repository and navigate to the project directory
----------------------------------------------------------------------------

.. code-block:: bash

    git clone [https://github.com/senlin-lin/SpatialZ.git] /path/to/your/SpatialZ_code
    cd /path/to/your/SpatialZ_code

Step 5: Install the project dependencies from requirements.txt
---------------------------------------------------------------

.. code-block:: bash

    pip install -r requirements.txt

Deploying a Docker Image on a New Server
=========================================

We also provide a Docker image that encapsulates our code and demo data, making it easier for users to directly download and use the provided resources. This image ensures a consistent and reproducible environment, allowing users to seamlessly run the code and explore the demo data without needing to configure dependencies or environments manually.

Step 1: Install Docker on the New Server
-----------------------------------------

The following commands illustrate the basic steps to install Docker on Ubuntu system (Ubuntu system required):

.. code-block:: bash

    sudo apt-get update
    sudo apt-get install docker-ce

Step 2: Pull the Image from Docker Hub
---------------------------------------

To download the Docker image, execute the following command:

.. code-block:: bash

    sudo docker pull linsenlin/spatialz:latest

Step 3: Launch the Docker Container on the New Server
------------------------------------------------------

Once the image is pulled, users can start the Docker container on the new server. The following command will run the container and map port 8888 of the server to port 8888 of the container:

.. code-block:: bash

    sudo docker run --gpus all -p 8888:8888 linsenlin/spatialz:latest

Step 4: Access Jupyter Notebook
--------------------------------

After launching the Docker container, users can access Jupyter Notebook by navigating to port 8888 on the server. If the server's IP address is 'server_ip', simply enter the following URL in a web browser:

`http://server_ip:8888`
