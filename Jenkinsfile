pipeline    {
    stages    {
        stage("Prepare"){
           echo "Hello World"
        }

        stage("Check version"){
            sh "docker --version"
        }

        stage("nuild image"){
            sh "docker build -t hello-nginx ."
        }
    }

}


