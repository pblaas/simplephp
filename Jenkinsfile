node {
    stage('Checkout'){
         print "Fase Checkout"
         git 'https://github.com/pblaas/simplephp.git'
    }

    stage('Build'){
      writeFile file: 'Dockerfile', text: 'FROM php:7.0-apache'
      def img = docker.build("pblaas/simpledemo:${env.BUILD_TAG}")
    }
} 
