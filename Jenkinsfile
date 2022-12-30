pipeline {
    agent any
    parameter {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], descriptio: '')
        booleanParam(name: 'executeTests', defaultvalue: true), description: '')
    }

    stages {
        stage('build') {
            steps {
                echo 'building the app..'
            }
        }
        
        stage('test') {
            when{
                expression{
                    params.executeTests
                }
            }
            steps {
                echo 'testing the app..'
            }
        }
        
        stage('deploy') {
            steps {
                echo 'deploying the app..'
                echo "deploying version ${params.VERSION}"
            }
        }
       
    }
    
   
}
