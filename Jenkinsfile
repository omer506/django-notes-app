pipeline {
    agent any
    stages{
        stage("Clone Code"){
            steps {
                echo "Cloning the code..............."
                git url:"https://github.com/omer506/django-notes-app.git", branch: "main"
            }
                
        }
        stage("Build Image"){
            steps {
                echo "Building the image..............."
                sh "docker build -t my-notes-app ."
            }
                
        }
        stage("Push to Docker Hub"){
            steps {
                echo "Pushing image to Docker Hub..............."
                withCredentials([usernamePassword(credentialsId:"dockerhub",passwordVariable:"dockerHubPass",usernameVariable:"dockerHubUser")]){
                sh "docker tag my-notes-app omernasim/my-notes-app:latest"
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                sh "docker push omernasim/my-notes-app:latest"
                }
            }
                
        }
        stage("Deploy"){
            steps {
                echo "Deploying the container..............."
                sh "docker-compose down && docker compose up -d"
            }
                
        }
        }
    }
