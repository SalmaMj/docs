pipeline {
    agent any
    tools {
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
    stages {
        stage('GIT') {
            steps {
                git branch: 'master', url: 'https://github.com/hwafa/timesheetproject.git'
            }
        }
        stage('Compile Stage') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('SonarQube Analysis') {
    steps {
        withSonarQubeEnv('Sonar') { 
            sh 'mvn sonar:sonar -Dsonar.login=$SONAR_TOKEN'
        }
    }
}

    }
}

