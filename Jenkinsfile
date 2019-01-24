podTemplate(label: 'jenkins-mvn-test', containers: [
    containerTemplate(name: 'maven', image: 'maven:3-jdk-8-alpine', command: 'cat', ttyEnabled: true),
],
volumes:[
    hostPathVolume(mountPath: '/var/run/docker.sock'  , hostPath: '/var/run/docker.sock'),
    hostPathVolume(mountPath: '/root/.m2/repository'     , hostPath: '/root/.m2/repository')
]){

  node ('jenkins-mvn-test') {

    // User Custom Setting ////////////////////////////////////////////////////////////////////////////////////////////////
  
    stage ('Maven Build') {
      container('maven') {
        sh 'ls -al'
      }
    }
  }
}
