pipeline {

  agent { label 'gcp-k8s' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/zedex11/playjenkins.git', branch:'test-deploy-stage'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
