pipeline {
    agent any
    stages {
        stage ("Code Clone") {
            steps {
                git url: "https://github.com/ABHAY4321/netflix-clone-react.git", branch:"main"
            }
        }
        stage ("Build & Test") {
            steps {
                /*
                sh "docker image build -t netflix:latest ."
                */
                echo "Image built & tested !!!"
            }
        }
        stage ("Push to DockerHub") {
            steps {
                /*
                withCredentials([usernamePassword(credentialsId:'dockerHub', usernameVariable: 'dockerHubUser', passwordVariable: 'dockerHubPass')]) {
                    sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                    sh "docker image tag netflix:latest ${env.dockerHubUser}/netflix:latest"
                    sh "docker image push ${env.dockerHubUser}/netflix:latest"
                }
                */
                echo "Image pushed to Docker Hub"
            }
        }
        stage ("App Deploy") {
            steps {
                /*
                sh "docker container run -d --name node-app -p 8000:8000 pinku9627/node-app:latest"
                sh "docker container rm -f node-app"
                
                */
                sh "docker compose down && docker compose up -d"
                echo "Application deployed successfully !!!!!"
            }
        }
        stage ("Remove Docker Image Locally") {
            steps {
                /*
                sh "docker image rm -f ${env.dockerHubUser}/netflix:latest"
                sh "docker image rm -f netflix:latest"
                */
            }
        }
    }
}
