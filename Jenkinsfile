podTemplate(label: 'jenkins-pipeline', containers: [
    containerTemplate(name: 'maven', image: 'maven:3-jdk-8-alpine', command: 'cat', ttyEnabled: true),
],
volumes:[
    hostPathVolume(mountPath: '/var/run/docker.sock'  , hostPath: '/var/run/docker.sock'),
    hostPathVolume(mountPath: '/home/jenkins/.m2'     , hostPath: '/root/.m2/repository')
]){

  node ('jenkins-pipeline') {

    // User Custom Setting ////////////////////////////////////////////////////////////////////////////////////////////////
  
    stage ('Maven Build') {
      container('maven') {
        sh 'cd /home/jenkins/.m2'
        sh 'rm -f ./target'
      }
    }
  }
}
