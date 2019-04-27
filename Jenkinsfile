pipeline {
  agent {
    kubernetes {
      label "pod-${UUID.randomUUID().toString()}"
      defaultContainer 'maven'
      yamlFile 'pipeline/KubernetesPod.yaml'
    }
  }
  stages {
    stage('Run maven') {
      steps {
        container('maven') {
          sh "echo MAVEN_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}"
          sh "mvn -version"
        }
      }
    }
  }
}