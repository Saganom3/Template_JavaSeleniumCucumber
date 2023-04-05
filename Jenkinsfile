pipeline {
  agent any

  stages {
    stage('Hello') {
      steps {
        echo 'Hello World'
        // Get some code from a GitHub repository
        git 'https://github.com/Saganom3/Template_JavaSeleniumCucumber.git'

        // Run Gradle on a Windoa agent.
        powershell "gradle -D"cucumber.options=--tags @Test" test"

        // To run Maven on a Windows agent, use
        // bat "mvn -Dmaven.test.failure.ignore=true clean package"      
      }
    }
  }
}
