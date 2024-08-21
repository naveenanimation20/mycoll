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
                sh 'newman run ./fileupload_coll.json  -g ./workspace.postman_globals.json -n 3 -r htmlextra,cli --reporter-htmlextra-export ./results/report.html'
            }
        }
        stage('Publish HTML Extra Report'){
            steps{
                     publishHTML([allowMissing: false,
                                  alwaysLinkToLastBuild: false, 
                                  keepAll: true, 
                                  reportDir: 'results', 
                                  reportFiles: 'report.html', 
                                  reportName: 'HTML Extra PL Report', 
                                  reportTitles: ''])
            }
        }
    }
}
