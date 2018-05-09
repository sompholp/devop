pipeline    {
    agent any
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
                sh "docker build -t hello-nginx ."
                sh "docker tag hello-nginx:1.${env.BUILD_NUMBER} hello-ngnix"
            }
        }
    }

}


