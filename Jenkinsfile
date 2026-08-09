node( label: 'linux' ) {
  stage('Check 3 : Artifact Deployment') {
    def fileName = "file.txt"
    sh "echo 'Hello World' > ${ fileName }"
    archiveArtifacts(artifacts: "${ fileName }", fingerprint: true)
    deployArtifacts(repo: 'thesis>testing', artifacts: "${ fileName }", metadata: [
      'groupId': 'io.github.venanocta.thesis',
      'artifactId': 'hello-world',
      'version': '1'
    ])
  }
}

