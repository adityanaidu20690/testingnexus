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

  stage('upload artifact') {
            steps {
nexusArtifactUploader artifacts: [[artifactId: 'addydevops', classifier: '', file: 'target/addydevops-1.0.1.war', type: 'war']], credentialsId: 'addydevops', groupId: 'addydevops', nexusUrl: '52.87.143.87:8081/', nexusVersion: 'nexus3', protocol: 'http', repository: 'addy-release', version: '1.0.1'
            }

        }
}
}
