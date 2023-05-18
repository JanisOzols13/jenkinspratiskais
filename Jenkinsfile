pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                echo 'instalēt pip atkaribas'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'ls python-greetings'
                powershell 'pip install -r python-greetings\\requirements.txt'
            }
        }
      stage('deploy-to-dev') {
          steps {
                echo 'uzstadisana uz dev'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-dev -p 7001'
                powershell 'pm2 delete all'
            }
        }
      stage('tests-on-dev') {
            steps {
                echo 'testesana uz dev'
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework.git'
                powershell 'npm install'
            }
        }
      stage('deploy-to-staging') {
            steps {
                echo 'uzstadisana uz dev'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7002'
                powershell 'pm2 delete all'               
            }
        }
      stage('tests-on-staging') {
            steps {
                echo 'testesana uz stage'
                powershell 'npm run'            
            }
        }
       stage('deploy-to-preprod') {
            steps {
                echo 'uzstadisana uz prepod'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7003'
                powershell 'pm2 delete all'
            }
        }
      stage('tests-on-preprod') {
          steps {
                echo 'testesana uz prepod'
                powershell 'npm run'   
            }
        }
      stage('deploy-to-prod') {
            steps {
                echo 'uzstadisana uz prod'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7004'
                powershell 'pm2 delete all'
            }
        }
      stage('tests-on-prod') {
          steps {
                echo 'ttestesana uz prod'
                powershell 'npm run'
            }
        }
    }
}
