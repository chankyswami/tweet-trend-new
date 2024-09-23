pipeline {
    agent {
        node {
            label "maven"
        }
    }
environment {
    JAVA_HOME = '/usr/lib/jvm/java-11-openjdk-amd64' // Replace with your actual JAVA_HOME path
    MAVEN_HOME = '/opt/apache-maven-3.9.9' // Replace with your actual Maven path
    PATH = "${MAVEN_HOME}/bin:${JAVA_HOME}/bin:${env.PATH}"
    }
//     PATH= "/usr/lib/jvm/java-11-openjdk-amd64/bin:$PATH"
//     PATH = "/opt/apache-maven-3.9.9/bin:$PATH"
// }
    stages {
        stage("build") {
            steps {
                sh 'java -version'
                sh 'mvn -version'
                sh 'mvn clean deploy'
            }
        }
//         stage('SonarQube analysis') {
//             environment {
//                 scannerHome = tool 'chanky-sonar-scanner' // must match the name of an actual scanner installation directory on your Jenkins build agent
//             }
//             steps {
//             withSonarQubeEnv('chanky-sonarqube-server') { // If you have configured more than one global server connection, you can specify its name as configured in Jenkins
//             sh "${scannerHome}/bin/sonar-scanner"
//             }
//             }
//   }
    }
}
