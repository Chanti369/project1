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
    }
}