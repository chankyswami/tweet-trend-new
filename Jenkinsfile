pipeline {
    agent {
        node {
            label "maven"
        }
    }
environment {
    PATH= "/usr/lib/jvm/java-11-openjdk-amd64/bin:$PATH"
    PATH = "/opt/apache-maven-3.9.9/bin:$PATH"
}
    stages {
        stage("build") {
            steps {
                sh 'mvn clean deploy'
            }
        }
        stage('SonarQube analysis') {
            environment {
                scannerHome = tool 'chanky-sonar-scanner' // must match the name of an actual scanner installation directory on your Jenkins build agent
            }
            steps {
            withSonarQubeEnv('chanky-sonarqube-server') { // If you have configured more than one global server connection, you can specify its name as configured in Jenkins
            sh "${scannerHome}/bin/sonar-scanner"
            }
            }
  }
    }
}
