pipeline {
  agent any
  stages {
    stage ('Inicializacion') {
      steps {
        echo 'Inicializando pipeline'
        sh 'pip -V'
        sh 'pip install coverage'
        sh 'pip list'
        sh 'coverage --version'
      }
    }
    stage ('Pruebas Unitarias') {
      steps {
        echo 'Realizando Pruebas'
      }
    }
    stage ('Construccion') {
      steps {
        echo 'Construyendo imagen'
      }
    }
    stage ('Publicacion') {
      steps {
        echo 'Publicando imagen'
      }
    }
    stage ('Aprobacion') {
      steps {
        timeout(time:5, unit:'DAYS'){
          input message: 'Aprobar Despliegue Canary?', submitter: 'DevOps'
        }
      }
    }
    stage ('Despliegue Produccion') {
      steps {
        echo 'Despliegue Produccion'
      }
    }
  }
}