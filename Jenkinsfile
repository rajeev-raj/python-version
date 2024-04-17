pipeline {
    agent any

    environment {
        // Declare an environment variable for Python version
        PYTHON_VERSION = ''
    }

    stages {
        stage('Initialize Environment') {
            steps {
                script {
                    // Call the custom method to set up the Python version environment variable
                    setupPythonVersion()
                }
            }
        }

        stage('Use Python Version') {
            steps {
                // Use the environment variable in your pipeline
                echo "Using Python Version: ${env.PYTHON_VERSION}"
            }
        }
    }
}

// Define a method to read and set the Python version from a YAML file
def setupPythonVersion() {
    // Read the YAML configuration file
    def configFile = readYaml file: 'config.yaml'
    
    // Update environment variable for Python version
    env.PYTHON_VERSION = configFile.pythonVersion

    // Optionally, log the Python version to check it's set
    echo "Python Version set to: ${env.PYTHON_VERSION}"
}
