node {
    stage 'Checkout'
         print "Fase Checkout"
         git 'https://github.com/pblaas/simplephp.git'
    

    stage 'Build'
      writeFile file: 'Dockerfile', text: 'FROM php:7.0-apache'
      def img = docker.build("pblaas/simpledemo:${env.BUILD_TAG}")
      docker.withRegistry('', 'docker-registry-login'){
        img.push('latest');
      }
     
    stage 'Deploy to cluster'
      sh("kubectl config set-credentials jenkins-build --token=`cat /var/run/secrets/kubernetes.io/serviceaccount/token`")
      sh("kubectl config set-cluster internal1 --server=https://kubernetes --certificate-authority=/var/run/secrets/kubernetes.io/serviceaccount/ca.crt")
      sh("kubectl config set-context default --user=jenkins-build --namespace=`cat /var/run/secrets/kubernetes.io/serviceaccount/namespace`  --cluster=internal1")
      sh("kubectl config use-context default")
}
