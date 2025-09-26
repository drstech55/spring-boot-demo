pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME'     // Make sure Maven is configured in Jenkins (Manage Jenkins → Global Tool Configuration)
        jdk 'JAVA_HOME'        // Make sure JDK is configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/drstech55/spring-boot-demo.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package -DskipTests'
            }
        }

        stage('Run') {
            steps {
                bat 'java -jar target\\spring-boot-demo-0.0.1-SNAPSHOT.jar'
            }
        }
    }
}
