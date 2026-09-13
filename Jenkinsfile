pipeline {
    agent { 
        node { 
            label 'ROBOSHOP' 
        } 
    }

    environment {
        COURSE = "Jenkins"
    }
   // Following is build section
    stages {
        stage('Build') {
            steps {

            script {
                    sh """
                echo 'Building..'
                 echo "Course is: ${COURSE}"
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