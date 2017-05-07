node {
    stage('Checkout'){
         print "Fase Checkout"
         git 'https://github.com/pblaas/simplephp.git'
    { 
    stage('Build'){
      writeFile file: 'Dockerfile', text: 'FROM php:7.0-apache'
      sh("docker build -t pblaas/simplephp:${env.BUILD_TAG} .")
    } 
}
