pipeline {
    agent {
     label 'ansible'
    }
    stages {
        stage('Download repository from GitHub') {
            steps {
                dir('vector') {
                    git branch: 'main', credentialsId: 'github', url: 'git@github.com:Vadim-Nazarov/vector.git'
                }
            }
        }
        stage ('Molecule test') {
            steps {
                sh 'molecule test'
            }
        }
    }
}
