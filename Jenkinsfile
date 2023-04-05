pipeline {
  agent any

  stages {
    stage('Eliminar workspace') {
      steps {
        deleteDir()
      }
    }

    stage('Clonar repositorio') {
      steps {
        echo 'Hello World'
        // Get some code from a GitHub repository
        git 'https://github.com/Saganom3/Template_JavaSeleniumCucumber.git'

      }
    }

    stage('Compilar y ejecutar pruebas') {
      steps {
        // Run Gradle on a Windoa agent.
        bat "./gradlew clean build test --rerun-tasks"

        // To run Maven on a Windows agent, use
        // bat "mvn -Dmaven.test.failure.ignore=true clean package"  
      }
    }
    stage('Generar reporte Cucumber') {
      steps {
        cucumber '**/*.json'
      }
    }
  }
}
