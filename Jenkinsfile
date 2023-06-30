pipeline {
    agent any

    stages {
        stage('code') {
            steps {
                // Fetch code from GitHub repository
                git 'https://github.com/MeghanaMahale/time-tracker.git'
            }
        }

        stage('Build') {
            steps {
                // Use Maven to build the project
                bat 'mvn clean package'
            }
        }
        
        stage('Deploy') {
            steps {
                // Copy the generated WAR file to Tomcat webapps folder
                bat 'copy "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\%JOB_NAME%\\web\\target\\*.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps"'
            }
        }
    }
}
