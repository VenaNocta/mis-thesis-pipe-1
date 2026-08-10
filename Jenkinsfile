node( label: 'linux' ) {
  checkout2(scm)
  stage('Check 7 : Git Repository Version Management') {
sh 'git config core.hooksPath githooks'
sh 'tree'
    if( !gitTagExists2( scm: scm, tag: 'v1.0.0' )) {
      // tag does not exist -> build and publish the project
      // published? -> set release version in git
      gitTagPush2(scm: scm, tag: 'v1.0.0',
          comment: '[artifact] io.github.venanocta.thesis:hello-world:1.0.0')
    }
  }
}

