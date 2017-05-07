node {
    git 'https://github.com/pblaas/simplephp.git'
    if (!fileExists ('Dockerfile')) {
      writeFile file: 'Dockerfile', text: 'FROM php:7.0-apache'
    }
    kubernetes.image().withName("simplephp").build().fromPath(".")
} 
