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
        stage('copy files'){
            steps{
                script{
                    sshagent(['ssh']) {
                        sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.7.147'
                        sh 'scp /var/lib/jenkins/workspace/p5/* ec2-user@172.31.7.147:/home/ec2-user/'
                    }
                }
            }
        }
        stage('run ansible'){
            steps{
                script{
                    sshagent(['ssh']) {
                        sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.7.147'
                        sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.7.147 cd /home/ec2-user/'
                        sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.7.147 ansible-playbook ansible.yml'
                    }
                }
            }
        }
    }
}