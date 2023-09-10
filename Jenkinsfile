pipeline {
    agent any 
    stages {
        stage('Static Analysis') {
            steps {
                script {
                    echo 'Run the static analysis to the code!'
                    def scannerHome = tool 'sonarscanner';
                    withSonarQubeEnv(installationName: 'sq1', envOnly: true) {
                        println "${env.SONAR_HOST_URL}"
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                } 
            }
        }
        stage('Compile') {
            steps {
                echo 'Compile the source code' 
            }
        }
        stage('Security Check') {
            steps {
                echo 'Run the security check against the application' 
            }
        }
        stage('Run Unit Tests') {
            steps {
                echo 'Run unit tests from the source code' 
            }
        }
        stage('Run Integration Tests') {
            steps {
                echo 'Run only crucial integration tests from the source code' 
            }
        }
        stage('Publish Artifacts') {
            steps {
                echo 'Save the assemblies generated from the compilation' 
            }
        }
    }
}