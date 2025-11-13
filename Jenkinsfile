pipeline{
    agent any

    stages{
        stage('Clone Code') {
            steps{
                // echo "Cloning the code!!!"
                git url: "https://github.com/TheRahulRaypure/node-todo-cicd.git", branch: "master"
            }
        }
        stage('Build') {
            steps{
                // echo "Build the code..."
                sh "docker build -t node-app"
            }
        }
        stage('Push to DockerHub') {
            steps{
                // echo "Push the image to the DockerHub..."
                withCredentials([usernamePassword(
                    credentialsID: "dockerHubCred", 
                    usernameVariable: "dockerHubUser", 
                    usrnamePassword:"dockerHubPass")]) {
                        sh "docker login -u ${env.dockerHubUser} -p ${dockerHubPass}"
                        sh "docker push therahulraypure/node-todo-app:latest"
                    }
            }            
        }
        stage('Deploy') {
            echo "Deploy the code..."
        }
    }
}