node {
    stage 'Checkout'
         print "Fase Checkout"
         git 'https://github.com/pblaas/simplephp.git'
    
    stage 'Build'
      writeFile file: 'Dockerfile', text: 'FROM php:7.0-apache'
      docker build -t ${DOCKER_HUB_USER}/simplephp:${env.BUILD_TAG} .

    stage 'Push to registry'
      docker login -u ${DOCKER_HUB_USER} -p ${DOCKER_HUB_PASSWORD}
      docker push ${DOCKER_HUB_USER}/simplephp:${env.BUILD_TAG}
     
}
