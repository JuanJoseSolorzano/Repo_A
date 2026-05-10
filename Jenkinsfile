pipeline {
    agent {
        label 'windows11_machine'
    }
    stages {
        stage('Push into master'){
            steps {
                script {
                    echo "Commit: ${env.GIT_COMMIT}"
                }
                powershell """
                    Write-Host 'A new release has been merged' 
                """ 
            }
        }
        stage('Trigger Repo_B'){
            steps {
                build job: 'Repo_B-Pipeline'
            }
        }
    }
}