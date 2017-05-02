node {
  parallel fivesix: {
    stage('Build Image : php5.6') {
      docker.withRegistry('https://jenkins.paulbunyan.net:5000', 'pbc-docker-registry') {
        checkout scm
        def img = docker.build('php:5.6', '. -f Dockerfile.56')
        img.push('5.6')
        img.push('5')
      }
    }
  }, sevenone: {
    stage('Build Image : php7.1') {
      docker.withRegistry('https://jenkins.paulbunyan.net:5000', 'pbc-docker-registry') {
        checkout scm
        def img = docker.build('php:7.1', '. -f Dockerfile.71')
        img.push('latest')
        img.push('7.1')
        img.push('7')
      }
    }
  }
}