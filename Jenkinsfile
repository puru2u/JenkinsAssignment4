pipeline {
    agent any
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

            stage('Run Application HelloWorld') {
                steps {
                    sh 'mvn exec:java -Dexec.mainClass="com.wipro.topgear.HelloWorld"'
                }
            }
            stage('Run Application HelloWipro') {
                 steps {
                    sh 'mvn exec:java -Dexec.mainClass="com.wipro.topgear.HelloWipro"'
                 }
            }
             stage('Run Application HelloJenkins') {
                 steps {
                    sh 'mvn exec:java -Dexec.mainClass="com.wipro.topgear.HelloJenkins"'
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