pipeline {
    agent {
        label 'windows11_machine'
    }
    stages {
        stage('Trigger Repo 1'){
            steps {
                bat 'echo TA repo triggered successfully'
            }
        }
        stage('Clone Repo_B'){
            steps {
                build job: 'Repo_B-Pipeline'
            }
        }
    }
}