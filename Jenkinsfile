pipeline {
    agent {
        label 'windows11_machine'
    }
    stages {
        stage('Push into master'){
            steps {
                script {
                    echo "================================="
                    echo "PIPELINE METADATA"
                    echo "================================="

                    echo "Job Name: ${env.JOB_NAME}"
                    echo "Build Number: ${env.BUILD_NUMBER}"
                    echo "Build URL: ${env.BUILD_URL}"

                    echo "Repository: ${env.GIT_URL}"
                    echo "Branch: ${env.GIT_BRANCH}"
                    echo "Commit: ${env.GIT_COMMIT}"

                    def shortCommit = env.GIT_COMMIT.take(7)

                    echo "Short Commit: ${shortCommit}"

                    echo "Agent: ${env.NODE_NAME}"
                    echo "Workspace: ${env.WORKSPACE}"

                    echo "================================="
                }
                powershell '''
                    Write-Host 'A new release has been merged' 
                '''
            }
        }
        stage('Trigger Repo_B'){
            steps {
                build job: 'Repo_B-Pipeline'
            }
        }
    }
}