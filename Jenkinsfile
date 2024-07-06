pipeline {

  agent {
    kubernetes {
      yamlFile 'jenkins-agent.yaml'
    }
  }
  
  environment {
    DOCKER_REGISTRY_DOMAIN = "dr-eye.tencentcloudcr.com"
    DOCKER_NAMESPACE = ""
    DOCKER_IMAGE_NAME = "test"
    DOCKER_IMAGE_TAG = ""
    DOCKER_IMAGE_URL = ""
    GIT_BRANCH_NAME = env.BRANCH_NAME
  }

  stages {

    stage('Kaniko Build & Push Image') {
      steps {
        container('git') {
          script {
            sh(script: 'pwd')
            sh(script: 'ls .')
            sh(script: 'ls ..')
            sh(script: 'git remote -v')
          }
        }
      }
    }
  }
}
