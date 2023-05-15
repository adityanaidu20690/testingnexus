pipeline {
    agent any

 stages {
        stage('git clone') {
            steps {
                git 'https://github.com/adityanaidu20690/testingnexus.git'
            }
        }
 stage('maven build') {
          steps {
               sh 'mvn clean install test package'
          }
         
        }

        stage('SonarQube Analysis') {
           
  steps{
   sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=addysonar \\
  -Dsonar.projectName=\'addysonar\' \\
  -Dsonar.host.url=http://3.80.73.45:9005 \\
  -Dsonar.token=sqp_e34fd86302a8e786b71cffaf435f5a36f7c34265'''
            }
  }
    stage('sast owasp') {
            steps {
              dependencyCheck additionalArguments: '''--project=test
--scan="/var/lib/jenkins/workspace/test"
--format="HTML"''', odcInstallation: 'default'
            }
        }

}
}
