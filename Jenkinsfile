node {
    git 'https://github.com/pblaas/simplephp.git'
    if (!fileExists ('Dockerfile')) {
      writeFile file: 'Dockerfile', text: 'FROM pblaas/nginx-alpine'
    }
    kubernetes.image().withName("simplephp").build().fromPath(".")
    #kubernetes.image().withName("simplephp").tag().inRepository("172.30.101.121:5000/default/simplephp").withTag("1.0")
    #kubernetes.image().withName("172.30.101.121:5000/default/example").push().withTag("1.0").toRegistry()
} 
