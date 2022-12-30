// Jenkinsfile for my-pipeline3-dockerhub
pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages {
        stage("build jar"){
            steps{
                echo "building the application..."
                sh 'mvn package'
            }
        }

        stage("build image"){
            steps{
                echo "building the docker image..."
                withCredentials([usernamePassword(credentialsId: 'docker-hub-repo',passwordVariable: 'PASS', usernameVariable:'USER')]){
                    sh 'docker build -t oluwaphemmy/my-repo:jma-2.0 .'
                    sh "echo $PASS | docker login -u $USER --password-stdin"
                    sh 'docker push oluwaphemmy/my-repo:jma-2.0'
                }
            }
        }

        stage("deploy"){
            steps{
                echo "deploying the application..."
            }
        }
    }
}
