node( label: 'linux' ) {
  stage('Check 1 : Build Environment') {
    def fileName = "file.txt"
    sh "echo 'Hello World' > ${ fileName }"
    sh "cat ${ fileName }"
    archiveArtifacts(artifacts: "${ fileName }", fingerprint: true)
		signArtifacts(artifacts: "${ fileName }")
    // load all archived files
    unarchive mapping: ['*':'./archive']
    sh 'ls -l ./archive'
    sh 'cat ./archive/*'
  }
}

