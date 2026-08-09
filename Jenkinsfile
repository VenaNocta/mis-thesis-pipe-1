node( label: 'linux' ) {
  repoProxy(['maven>central': 'central']) {
    checkout2(scm)
    stage('Check 6 : Dynamic Artifact Loading & Inspection : Valid vs Invalid Artifact with Maven') {
      sh "echo '-s \"$WORKSPACE/.mvn/settings.xml\"' >> .mvn/maven.config"
      sh 'printenv | grep PROXY'
      // version 1.1.2
      sh 'mvn net.runeduniverse.tools.maven.r4m:r4m-maven-extension:1.1.2:help'
      // version 1.0.0
      sh 'mvn net.runeduniverse.tools.maven.r4m:r4m-maven-extension:1.0.0:help'
    }
  }
}

