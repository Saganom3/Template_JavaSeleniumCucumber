pipeline {
  agent any

  stages {
    stage('Hello') {
      steps {
        echo 'Hello World'
        // Get some code from a GitHub repository
        git 'https://github.com/Saganom3/Template_JavaSeleniumCucumber.git'

        // Run Maven on a Unix agent.
        sh "gradle clean"

      }
    }
  }
}
