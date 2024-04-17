pipeline {
    agent any

    stages {
        stage('Check Python Version - Stage 1') {
            steps {
                script {
                    sh 'echo "Stage 1: Checking Python version"'
                    sh 'python --version || python3 --version'
                }
            }
        }
        
        stage('Check if config.xml is present') {
            steps {
                script {
                        if(fileExists('config.xml')) {
                        echo "config.xml file is present."
                        } 
                        else 
                        {
                        echo "config.yaml file is not present."
                        error("config.yaml file is missing.")
                    }
                }
            }
        }
        
        stage('Check Python Version - Stage 3') {
            steps {
                script {
                    sh 'echo "Stage 3: Checking Python version"'
                    sh 'python --version || python3 --version'
                }
            }
        }
    }
    
    post {
        always {
            echo 'Finished checking Python versions across stages.'
        }
    }
}
