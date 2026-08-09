node( label: 'linux' ) {
	repoProxy(['maven>central': 'central', 'maven>runeduniverse>maven-thesis-testing': 'testing']) {
	bundleContext {
		stage('Checkout SCM') {
			checkout2(scm)
			sh "echo '-s \"$WORKSPACE/.mvn/settings.xml\"' >> .mvn/maven.config"
		}
		stage('Where am I?') {
			sh 'uname -a'
			sh 'printenv | grep PROXY'
			sh 'pwd'
			sh '/usr/sbin/ip a'
		}
		stage('Repo Check') {
			sh 'mkdir results'
			sh 'curl -D - -L -o results/r4m-maven-extension-1.0.0.jar https://repo1.maven.org/maven2/net/runeduniverse/tools/maven/r4m/r4m-maven-extension/1.0.0/r4m-maven-extension-1.0.0.jar'
			sh 'sha1sum results/r4m-maven-extension-1.0.0.jar'
		}
		stage('Maven Check') {
			sh 'mvn net.runeduniverse.tools.maven.r4m:r4m-maven-extension:help'
		}
// deployment repo id: 'thesis>testing'

	}}
}
