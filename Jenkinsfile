pipeline{
    agent any
    stages{
        stage('Clone Code'){
            steps{
                echo "Cloning the code!!!"
                git url: "https://github.com/TheRahulRaypure/node-todo-cicd.git", branch: "master"
            }
        }

        stage('Build') {
            steps{
                echo "Build the code..."
            }
        }

        stage('Test') {
            echo "Test the code..."
        }

        stage('Deploy') {
            echo "Deploy the code..."
        }
    }
}