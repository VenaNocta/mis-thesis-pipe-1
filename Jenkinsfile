node( label: 'linux' ) {
  bundleContext {
    stage('Check 3 : Artifact Deployment') {
      def fileName = "file.txt"
      sh "echo 'Hello World' > ${ fileName }"
      sh "base64 ${ fileName } > ${ fileName }.encoded"
      archiveArtifacts(artifacts: "${ fileName }*", fingerprint: true)
      bundleArtifacts(bundle: "files", artifacts: "${ fileName }*", metadata: [
        'groupId': 'io.github.venanocta.thesis',
        'artifactId': 'hello-world',
        'version': '1'
      ])
      deployArtifacts(repo: 'thesis>testing', bundle: "files")
    }
  }
}

