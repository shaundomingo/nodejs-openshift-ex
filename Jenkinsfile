#!groovy

node {

  checkout scm
  
  stage('build') {
    openshiftBuild bldCfg: 'nodejs-openshift-ex', checkForTriggeredDeployments: 'true', namespace: 'nodejs-demo', showBuildLogs: 'true', verbose: 'false', waitTime: '600', waitUnit: 'sec'
  }

  stage('test') {
    sh "echo 'Run tests'"
  }

  stage('deploy') {
    openshiftDeploy deploymentConfig: 'nodejs-openshift-ex'
  }

}
