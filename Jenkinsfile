pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Our 1st build"'
                sh 'singularity build python3.simg python3.def'
            }
        }
       stage('test') {
            steps {
                sh 'singularity exec python3.simg  python --version'
            }
        }
        stage('Delpoy') {
            steps {
                sh 'echo "We are in deployement "'
            }
        }
    }
       post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
