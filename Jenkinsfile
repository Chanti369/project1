pipeline{
    agent any
    stages{
        stage('git checkout'){
            steps{
                script{
                    git branch: 'main', url: 'https://github.com/Chanti369/project1.git'
                }
            }
        }
        stage('establish ssh'){
            steps{
                script{
                    sshagent(['ssh']) {
                        sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.7.147'
                    }
                }
            }
        }
    }
}