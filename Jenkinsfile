podTemplate(label: 'jenkins-pipeline', containers: [
    containerTemplate(name: 'maven', image: 'maven:3-jdk-8-alpine', command: 'cat', ttyEnabled: true),
    containerTemplate(name: 'docker', image: 'docker:1.12', command: 'cat', ttyEnabled: true),
    containerTemplate(name: 'helm', image: 'lachlanevenson/k8s-helm:v2.7.0', command: 'cat', ttyEnabled: true),
    containerTemplate(name: 'kubectl', image: 'lachlanevenson/k8s-kubectl:v1.9.3', command: 'cat', ttyEnabled: true)
],
volumes:[
    hostPathVolume(mountPath: '/var/run/docker.sock'  , hostPath: '/var/run/docker.sock'),
]){

  node ('jenkins-pipeline') {

    // User Custom Setting ////////////////////////////////////////////////////////////////////////////////////////////////

    stage ('Maven Build') {
      container('maven') {
        sh 'ls -al'
      }
    }
  }
}
