pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                openshiftBuild(buildConfig: 'simplephp', showBuildLogs: 'true', namespace: 'development')
            }
        }
        stage('Deploy') {
            steps {
                openshiftDeploy(deploymentConfig: 'simplephp', namespace: 'development')
            }
        }
    }
}
