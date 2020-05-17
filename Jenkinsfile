pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                
                sh 'printenv'
                withMaven(maven : 'maven_3_5_0') {
                    bat "mvn package"
                    sh 'mvn clean compile'
                    
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn install'
                }
            }
        }
    }
}