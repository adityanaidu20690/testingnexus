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


}
}
