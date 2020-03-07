pipeline {
  agent any
  stages {
    stage('检出') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: env.GIT_BUILD_REF]], 
                                                                    userRemoteConfigs: [[url: env.GIT_REPO_URL, credentialsId: '7c086008-3d9b-4f09-b65a-f2e8893fcd31']]])
      }
    }
    stage('构建') {
      steps {
        echo '构建中...'
        sh 'yarn install'
        sh 'yarn build'
        echo '构建完成.'
      }
    }
    stage('部署') {
      steps {
        withCredentials(bindings: [certificate(credentialsId: '7c086008-3d9b-4f09-b65a-f2e8893fcd31')]) {
          echo '部署中...'
          sh 'env'
          sh 'scp -r . root@118.31.120.114:/data/wwwroot/api-spec'
        	echo '部署完成'
        }
      }
    }
  }
}