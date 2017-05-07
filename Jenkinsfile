node {
    git 'https://github.com/pblaas/simplephp.git'
    if (!fileExists ('Dockerfile')) {
      writeFile file: 'Dockerfile', text: 'FROM pblaas/nginx-alpine'
    }
    kubernetes.image().withName("simplephp").build().fromPath(".")
} 
