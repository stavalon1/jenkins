pipeline {
    agent any

    triggers {
        pollSCM '* * * * *'
    }
       stages {
        stage('initws') {
            steps {
                // clean workspace before init
                cleanWs()
            }
        }
           stage('gitinit') {
            steps {
                echo 'clone the code from github'
                git branch: 'main', url: 'https://github.com/Elad0109/simple-webapp-nodejs-.git'
            }
        }
           stage('build') {
            steps {
                // run build
                nodejs('nodejs18') {
                sh "npm install"
        }
            }
        }
        
        stage('test') {
            steps {
                // run testing
                nodejs('nodejs18') {
                sh "npm run test"
                echo "hey2223"
        }
            }
        }
        
                stage('deploy') {
            steps {
                // start the app 
                nodejs('nodejs18') {
                sh "npm run start"
        }
            }
                }
          
        
       }
    }
