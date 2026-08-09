node( label: 'linux' ) {
	repoProxy(['maven>central': 'central', 'maven>runeduniverse>maven-thesis-testing': 'testing']) {
	bundleContext {
		stage('Checkout SCM') {
			checkout2(scm)
			writeFile(file: '.mvn/maven.config', text: "-s $WORKSPACE/.mvn/settings.xml")
		}
		stage('Where am I?') {
			sh 'uname -a'
			sh 'printenv | grep PROXY'
			sh 'pwd'
			sh '/usr/sbin/ip a'
		}
		stage('Repo Check') {
		}
		stage('Maven Check') {
			sh 'mkdir -p $HOME/.m2'
			sh 'ls -la /srv/jenkins'
			sh 'ls -la /srv/jenkins/.m2'
			sh 'ls -la /srv/jenkins/.m2/repository'
			sh 'mvn net.runeduniverse.tools.maven.r4m:r4m-maven-extension:help -X'
		}
// deployment repo id: 'thesis>testing'

	}}
}
