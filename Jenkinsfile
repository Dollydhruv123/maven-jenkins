pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                script {
                    sh "git clone -b master https://github.com/vimallinuxworld13/simple-java-maven-app.git"
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'maven clean'
                    // ABC indicates the folder name where the pom.xml file resides
                    sh 'mvn -f /var/lib/jenkins/workspace/maven-jenkins/simple-java-maven-app/pom.xml clean install'  
                }
            }
        }

        stage('Validate') {
            steps {
                script {
                    dir("/var/lib/jenkins/workspace/maven-jenkins/simple-java-maven-app/") {
                    sh "mvn validate"
                    sh "mvn compile"
                    }
                }
            }
        }
    }
}

