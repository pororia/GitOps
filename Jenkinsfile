pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/pororia/GitOps will replace by sed command before RUN
        git url: 'https://github.com/pororia/GitOps', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}