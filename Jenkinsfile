pipeline    {
    agent any
    environment{
        imageName = "somphol123p/hello-nginx"
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

        stage("build image"){
            steps   {
                sh "docker build -t ${env.imageName} ."
                sh "docker tag ${env.imageName} ${env.imageName}:1.${env.BUILD_NUMBER}"
            }
        }

        stage("push image"){
            steps   {
                sh "docker login -u sompholp -p passw0rd"
                sh "docker push ${env.imageName}"
            } 
        }
    }

}


