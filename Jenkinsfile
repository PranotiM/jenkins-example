pipeline {
    agent any

    stages {
        stage ('Validate Stage')
        {
            steps
            {
                withMaven(maven : 'LocalMaven')
                {
                    sh 'mvn validate'
                }
            }
        } 
    
    
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn install'
                }
            }
        }
    }
}
