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
                sh "docker build -t hello-nginx:1.2 ."
            }
        }
    }

}


