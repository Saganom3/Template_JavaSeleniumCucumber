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
        powershell "gradle clean test"

        // To run Maven on a Windows agent, use
        // bat "mvn -Dmaven.test.failure.ignore=true clean package"  
      }
    }
    stage('Generar reporte Cucumber') {
      steps {
        cucumber 'build/reports/cucumber'
      }
    }
    stage('Publicar informe de Cucumber') {
      steps {
        publishHTML(target: [
          allowMissing: false,
          alwaysLinkToLastBuild: true,
          keepAll: true,
          reportDir: 'build/reports/cucumber',
          reportFiles: 'index.html',
          reportName: 'Informe de Cucumber'
        ])
      }
    }
  }
}
