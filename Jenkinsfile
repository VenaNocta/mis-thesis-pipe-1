node( label: 'linux' ) {
	stage('Checkout SCM') {
		checkout2(scm)
		sh "echo '-s \"$WORKSPACE/.mvn/settings.xml\"' >> .mvn/maven.config"
	}
	stage('Where am I?') {
		sh 'whoami'
		sh 'uname -a'
		sh 'pwd'
		sh '/usr/sbin/ip a'
		sh 'printenv'
	}

	repoProxy(['maven>central': 'central', 'maven>runeduniverse>maven-thesis-testing': 'testing']) {
		sh 'printenv | grep PROXY'
		stage('Maven Check') {
			sh 'mvn net.runeduniverse.tools.maven.r4m:r4m-maven-extension:help'
		}

	bundleContext {
// deployment repo id: 'thesis>testing'

	}}
}
