node( label: 'linux' ) {
  bundleContext {
    stage('Check 3 : Artifact Deployment') {
      sh "echo 'Hello World' > file.txt"
      sh 'base64 file.txt > file.encoded'
      archiveArtifacts(artifacts: 'file.*', fingerprint: true)
      bundleArtifacts(bundle: "files", artifacts: 'file.*', metadata: [
        'groupId':    'io.github.venanocta.thesis',
        'artifactId': 'hello-world',
        'version':    '1'
      ])
      deployArtifacts(repo: 'thesis>testing', bundle: "files")
    }
  }
}

