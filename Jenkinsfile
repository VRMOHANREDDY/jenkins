pipeline {
    agent { 
        node { 
            label 'ROBOSHOP' 
        } 
    }

    environment {
        COURSE = "Jenkins"
    }
    options {
        disableConcurrentBuilds()
        timeout(time: 15, unit: 'MINUTES')
    }
        parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
   // Following is build section
    stages {
        stage('Build') {
            steps {

            script {
                    sh """
                echo 'Building..'
                 echo "Course is: ${COURSE}"
                 echo "Hello ${params.PERSON}"
                 echo "Biography: ${params.BIOGRAPHY}"
                 echo "Toggle: ${params.TOGGLE}"
                 echo "Choice: ${params.CHOICE}"
                 echo "Password: ${params.PASSWORD}"
                 echo "hey ram webhook triggered"
                 """
            }
          
            }
        }
        stage('Test') {
            steps {
            script {
                    sh """
                echo 'Testing..'
                 """
            }
            }
        }
        stage('Deploy') {
            steps {
            script {
                    sh """
                echo 'Deploy.'
                 """
            }
            }
        }
    }
 //   Post build section
        post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success { 
            echo 'I will run when success'
        }
        failure { 
            echo 'I will Run when it is failed'
        }
    }
}