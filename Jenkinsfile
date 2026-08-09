node( label: 'linux' ) {
  repoProxy(['maven>runeduniverse>maven-thesis-testing': 'testing']) {
    stage('Check 4 : Dynamic Artifact Loading & Inspection : Repo-Proxy') {
      def fileName = "file.txt"
      sh 'printenv | grep PROXY'
      sh "curl -D - -L -o ${fileName} ${MVN_PROXY_testing_URL}io/github/venanocta/thesis/hello-world/1/hello-world-1.txt"
      sh "cat ${fileName}"
    }
  }
}

