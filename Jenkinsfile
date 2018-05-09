pipeline    {
    agent any
    environment{
        imageName = "hello-nginx"
    }
    stages    {
        stage("Prepare"){
           steps {
               echo "Hello World"
           }
        }

        stage("Check version"){
            steps   {
                sh "docker --version"
            }
        }

        stage("bnuild image"){
            steps   {
                sh "docker build -t ${env.imageName} ."
                sh "docker tag ${env.imageName}:1.${env.BUILD_NUMBER} ${env.imageName}"
            }
        }
    }

}


