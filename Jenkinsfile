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
                scripts {
                    docker.withRegistry('https://registry.hub.docker.com','somphol123p')
                        {
                            def image = docker.build("${env.imageName}:1.${env.BUILD_NUMBER}")
                            image.push{}
                        }
                } 
            }   
        }
    }
}


