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
                powershell 'pm2 start python-greetings/app.py --name greetings-app-dev -p 7001'
                powershell 'pm2 delete all'
                echo 'deploying to development'
            }
        }
      stage('tests-on-dev') {
            steps {
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework.git'

                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hello-workd-pileline@2\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hello-workd-pileline\\ '

                powershell 'npm install'
                echo 'testing on development'
            }
        }
      stage('deploy-to-staging') {
            steps {
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7002'
                powershell 'pm2 delete all'
                echo 'deploying on stage'
            }
        }
      stage('tests-on-staging') {
            steps {
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework.git'

                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hello-workd-pileline\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hello-workd-pileline\\ '

                powershell 'npm install'
                echo 'testing on preprodoction'
            }
        }
       stage('deploy-to-preprod') {
            steps {
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7003'
                powershell 'pm2 delete all'
                echo 'deploying on stage'
            }
        }
      stage('tests-on-preprod') {
            steps {
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework.git'

                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hello-workd-pileline\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hello-workd-pileline\\ '

                powershell 'npm install'
                echo 'testing on preprodoction'
            }
        }
      stage('deploy-to-prod') {
            steps {
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7004'
                powershell 'pm2 delete all'
                echo 'deploying to prodoction'
            }
        }
      stage('tests-on-prod') {
            steps {
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework.git'

                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hello-workd-pileline\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hello-workd-pileline\\ '

                powershell 'npm install'
                echo 'tests on prodoction'
            }
        }
    }
}
