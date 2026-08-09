def artifactData(groupId, artifactId, version) {
  def map = [];
  map.file = "${ artifactId }-${ version }.jar";
  map.url = "${ MVN_PROXY_central_URL }" +
      "${ groupId.replace('.', '/') }/${ version }/" +
      map.file;
  return map;
}

node( label: 'linux' ) {
  repoProxy(['maven>central': 'central']) {
    stage('Check 5 : Dynamic Artifact Loading & Inspection : Valid vs Invalid Artifact') {
      sh 'printenv | grep PROXY'
      // version 1.1.2
      def data = artifactData(
          'net.runeduniverse.tools.maven.r4m', 'r4m-maven-extension', '1.1.2');
      sh "curl -D - -L -o ${ data.file } ${ data.url }"
      sh "sha1sum ${ data.file }"
      // version 1.0.0
      data = artifactData(
          'net.runeduniverse.tools.maven.r4m', 'r4m-maven-extension', '1.0.0');
      sh "curl -D - -L -o ${ data.file } ${ data.url }"
      // next line might not be executed in time ...
      sh "cat ${ data.file }"
    }
  }
}

