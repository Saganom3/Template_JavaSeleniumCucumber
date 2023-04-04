pipeline {
  agent any

  tools {
    // Install the Maven version configured as "M3" and add it to the path.
    gradle "Gradle"
  }

  stages {
    stage('Build') {
      steps {
        // Get some code from a GitHub repository
        git 'https://github.com/Saganom3/Template_JavaSeleniumCucumber.git'

        // Run Maven on a Unix agent.
        sh "gradle clean"

        // To run Maven on a Windows agent, use
        // bat "mvn -Dmaven.test.failure.ignore=true clean package"
      }

      stage('Construir con Gradle') {
        steps {
          echo "Se ejecuto exitosamente"
        }
      }
    }
  }
}
