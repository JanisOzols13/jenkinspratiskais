pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'ls python-greetings'
                powershell 'pip install -r python-greetings\\requirements.txt'
                echo 'Installing pip dependencies'
            }
        }
      stage('deploy-to-dev') {
            steps {
                echo 'deploying to development'
            }
        }
      stage('tests-on-dev') {
            steps {
                echo 'testing on development'
            }
        }
      stage('deploy-to-staging') {
            steps {
                echo 'deploying on stage'
            }
        }
      stage('tests-on-preprod') {
            steps {
                echo 'testing on preprodoction'
            }
        }
      stage('deploy-to-prod') {
            steps {
                echo 'deploying to prodoction'
            }
        }
      stage('tests-on-prod') {
            steps {
                echo 'tests on prodoction'
            }
        }
    }
}
