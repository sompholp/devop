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

        // stage("deploy"){
        //     steps {
        //         sshagent(['uat-server']) {
        //             sh "ls -lrt"
        //         }
        //     } 
        // }

        stage("deploy"){
            steps {
                sshagent(credentials: ['uat-server']) {
                    sh "ssh core@167.99.237.229 docker pull ${env.imageName}"
                }
            } 
        }
        
        // stage("build image"){
        //     steps   {
        //         sh "docker build -t ${env.imageName} ."
        //         sh "docker tag ${env.imageName} ${env.imageName}:1.${env.BUILD_NUMBER}"
        //     }
        // }

        // stage("push image"){
        //     steps   {
        //         script {
        //             docker.withRegistry('https://registry.hub.docker.com', 'somphol123p')
        //                 {
        //                     def image = docker.build("${env.imageName}","${env.imageName}:1.${env.BUILD_NUMBER}")
        //                     image.push{}
        //                 }
        //         } 
        //     }   
        // }
    }
}


