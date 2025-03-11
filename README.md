**Project Setup Guide**

Prerequisites

Ensure you have the following installed on your system:

Docker
Docker Compose
Jenkins

**Cloning the Repository:**

git clone https://github.com/omer506/<your-repo-name>.git
cd <your-repo-name>

**Environment Variables:**

Create a .env file in the root directory and configure necessary environment variables as per your setup.

Running the Application Locally with Docker Compose

docker-compose up -d --build

This will start the required services including the application, MySQL, and Nginx.

**Jenkins Configuration:**

Add Git Repository to Jenkins

Open Jenkins and navigate to Manage Jenkins > Plugins Manager.

Install Pipeline and Git Plugin if not already installed.

Go to New Item > Select Pipeline > Provide a name and click OK.

Under Pipeline Definition, select Pipeline script from SCM.

In SCM, select Git and enter the repository URL:

https://github.com/omer506/<your-repo-name>.git

Set Branch Specifier to the desired branch (e.g., */main or */master).

Set the Script Path to Jenkinsfile.

Click Save and Build Now to trigger the pipeline.

**Deployment Using Jenkins:**

The Jenkins pipeline is defined in the Jenkinsfile, which automates building and deploying the project. Ensure the Jenkinsfile contains necessary steps for your build and deployment process.

Stopping the Application

docker-compose down

**Additional Notes:**

Ensure that .env is correctly configured before running the application.

Modify the docker-compose.yml file if you need to change configurations.

Update the Jenkinsfile as per your CI/CD requirements.


