pipeline {
    agent any
    tools {
            maven 'Maven3'   // Name from Global Tool Configuration
            jdk 'JDK17'      // Name from Global Tool Configuration
        }

        environment {
            MAVEN_OPTS = "-Xmx1024m"
        }
    stages {
            stage('Checkout') {
                steps {
                    git url: 'https://github.com/puru2u/JenkinsAssignment4.git', branch: 'main'
                }
            }

            stage('Build') {
                steps {
                    sh 'mvn clean install'
                }
            }

            stage('Run Application') {
                steps {
                    sh 'mvn exec:java -Dexec.mainClass="com.wipro.topgear.HelloWorld"'
                }
            }
    }


    post {
           success {
               echo "Build and execution completed successfully."
           }
           failure {
               echo "Build or execution failed."
           }
    }
}