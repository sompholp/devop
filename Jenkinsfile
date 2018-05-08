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

        stage("nuild image"){
            steps   {
                sh "docker build -t hello-nginx ."
            }
        }
    }

}


