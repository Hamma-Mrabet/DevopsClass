pipeline {
    agent any
    tools{
        maven "M2_HOME"
    }
    stages {
        stage('GIT') {
            steps {
                git branch: "master",
                url: "https://github.com/hwafa/timesheetproject.git"
            }
        }
        stage('Scan') {
            steps {
                withSonarQubeEnv(installationName: 'sq1'){
                                 
                sh 'mvn sonar:sonar'
                                 }
            }
        }
    }
}
