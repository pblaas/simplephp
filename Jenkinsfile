node('agent'){
  def apiURL = 'https://192.168.2.22:8443'
  def namespace = 'development'

  stage 'Build'
  def buildConfig = 'simplephp'
  step new com.openshift.jenkins.plugins.pipeline.OpenShiftBuilder(apiURL, buildConfig, namespace, '', 'false', '', '', 'false', '')
  echo 'build'

  stage 'Deploy'
  def deploymentConfig = 'simplephp'
  step new com.openshift.jenkins.plugins.pipeline.OpenShiftDeployer(apiURL, deploymentConfig, namespace, '', '')
  echo 'deployed'
}
