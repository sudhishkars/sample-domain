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

            sh "mvn $MVN_ARGS -X -Pstandalone-agent -Djavax.net.debug=all mule:deploy -Dmule.artifact=target/sample-domain-1.0.0-SNAPSHOT-mule-domain.jar"
          }
        }
      }
    }    
}