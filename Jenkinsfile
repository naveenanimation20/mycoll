pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/naveenanimation20/mycoll'
            }
        }
        stage('Run Newman') {
            steps {
                sh 'newman run ./fileupload_coll.json  -g ./workspace.postman_globals.json -n 3 -r htmlextra,cli'
            }
        }
    }
}