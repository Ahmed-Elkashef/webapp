pipeline {
  agent any
  tools {
    maven 'Maven'
  }
  stages {
    
    stage ('Initialize') {
      steps {
        sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
            ''' 
      }
    }
    
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    
    stage ('Deploy-To-Tomcat') {
      steps {
        sh 'cp target/*.war /prod/apache-tomcat-8.5.64/webapps/'     
      }       
    }
    
  }
}
