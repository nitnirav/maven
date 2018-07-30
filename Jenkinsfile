pipeline {
    agent any

    stages {
        stage('compile stage')
        {
            steps {
                echo 'Building..'
                withMaven(Maven:'localMaven')
                   {
                    sh 'mvn test compile'
                   }
                    
                 }
        }
        stage('Test') {
            steps {
                echo 'Testing. '
                withMaven(Maven:'localMaven')
                   {
                    sh 'mvn test'
                   }
            }
        }
          stage('Deploy') {
            steps {
                echo 'Deploying....'
                withMaven(Maven:'localMaven')
                   {
                    sh 'mvn deploy'
                   }
            }
        }
    }
}
