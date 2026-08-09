node( label: 'linux' ) {
	repoProxy(['maven>central': 'central', 'maven>runeduniverse>maven-thesis-testing': 'testing']) {
	bundleContext {

		env.setProperty('PATH+SBIN', "/usr/sbin/")

		stage('Checkout SCM') {
			checkout2(scm)
		}

		stage('Where am I?') {
			sh 'uname -a'
			sh 'printenv | grep PROXY'
			sh 'pwd'
			sh 'ip a'
		}

// deployment repo id: 'thesis>testing'

	}}
}
