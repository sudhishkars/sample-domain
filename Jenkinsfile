pipeline {
    agent any

    tools {
        maven "mvn-385"
    }
    environment {
        MVN_ARGS = "${mwDefaults.mvnArgs}"
    }

    stages {

      stage('deploy') {
        steps {
          script {
            sh "mvn $MVN_ARGS clean package"

            sh "mvn $MVN_ARGS -Pstandalone-agent mule:deploy -Dmule.artifact=target/*.jar"
          }
        }
      }
    }    
}