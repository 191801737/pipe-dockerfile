
pipeline {
    agent any
    options {
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '7', numToKeepStr: '10')
        timestamps ()
    }
    parameters {
        string(name: 'BUILD_USER', defaultValue: 'staging', description: 'Used to distinguish between different environments')
        string(name: 'GSLB', defaultValue: 'gsb', description: 'gsb or pri')
    }
    stages {
        stage('pytest') {
            steps {
                sh 'chmod 744 ./config.sh'
                sh "./config.sh"
                sh "python config.py"
            }
        }
    }
}

