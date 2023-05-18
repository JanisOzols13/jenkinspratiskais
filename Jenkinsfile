pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                echo 'Installing pip dependencies'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'ls python-greetings'
                powershell 'pip install -r python-greetings\\requirements.txt'
            }
        }
      stage('deploy-to-dev') {
          steps {
                echo 'deploying to development'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-dev -p 7001'
                powershell 'pm2 delete all'
            }
        }
      stage('tests-on-dev') {
            steps {
                echo 'testing on development'
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework.git'
                powershell 'npm install'
            }
        }
      stage('deploy-to-staging') {
            steps {
                echo 'deploying on stage'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7002'
                powershell 'pm2 delete all'               
            }
        }
      stage('tests-on-staging') {
            steps {
                echo 'testing on preprodoction'
                powershell 'npm run'            
            }
        }
       stage('deploy-to-preprod') {
            steps {
                echo 'deploying on stage'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7003'
                powershell 'pm2 delete all'
            }
        }
      stage('tests-on-preprod') {
          steps {
                echo 'testing on preprodoction'
                powershell 'npm run'   
            }
        }
      stage('deploy-to-prod') {
            steps {
                echo 'deploying to prodoction'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7004'
                powershell 'pm2 delete all'
            }
        }
      stage('tests-on-prod') {
          steps {
                echo 'tests on prodoction'
                powershell 'npm run'
            }
        }
    }
}
