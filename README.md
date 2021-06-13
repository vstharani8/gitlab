# **Install Gitlab Service**

## **Architecture**

![diagram](./images/Architecture.jpg)

This is the simple architecture to install the GitLab Service using the Docker engine as per the below.
  * In the Linux Virtual machine, installed a Docker engine to create the containers. 
  * Pulling the GitLab Image from the docker registry. 
  * Creating the persistent volumes using the host volume. 


## **Prerequistes**

* Docker
* Docker Compose

## **Installation**

### **Installation Method**

we can install the GitLab service in two different ways based on the requirement.
1.	Install the GitLab service (HTTP) – Only for Testing
2.	Install the GitLab service (HTTPS) - Production

### 1. Install the GitLab service (HTTP) 


* Clone the repo in your machine.

```
git clone https://github.com/vstharani8/gitlab.git
```
* Setup the volume location for the Data and Logs

  1. Create the directory where you want to store the data for the GitLab.
  2. Configure a new environment variable $GITLAB_HOME pointint to the directory
      ```
      export GITLAB_HOME=/opt/gitlab
      ```
* Go to that folder where you clone the repo. Make sure docker-compose.yml file exists in the folder and run the below command to install the GitLab service as a container.
    ```
    docker-compose up -d
    ```
* The initialization process will take time and you can track the progress with the below command
    ```
     docker logs -f container_name
    ```
* After that, browse the web page using your IP address
    ```
     http://IP_Address
    ```
* When you log in to GitLab first time, will ask to set the admin password. After you change, you can login with your username (root) and password


