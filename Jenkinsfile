pipeline {
    agent any
    stages{
        stage('Cloning repository') {
            steps {
                git credentialsId: '06f153ab-eaab-493a-b9ba-deb3195466bd', url: 'https://github.com/4iglance/linux.git'
            }
        }

        stage('Execute script 1.sh') {
            steps {
                script {
                    sh "chmod 755 script1/1.sh"
                    sh "./script1/1.sh"
                }
            }
        }

        stage ('Create a file in workspace') {
            steps {
                script {
                    sh "echo \"This has been created by Jenkins pipeline\" > demo_pipeline1.txt"
                }
            }
        }
        stage ('Archive') {
            steps {
                archiveArtifacts 'demo_pipeline1.txt'
            }
        }
    }
}
