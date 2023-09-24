pipeline {
	agent {
		label {
			label "built-in"
			 customWorkspace "/mnt/keshav2/"
			 }
			}
    stages {
        stage ('clean Workspace') {
         steps {
                cleanWs()
                }
            }
        stage ('master') {
			steps {
			  sh "git clone https://github.com/keshavkale123/my-app.git"
			  sh " cp -r /mnt/keshav2/my-app/index.html /var/www/html/"
		      sh " chmod -R 777 /var/www/html "
			  }
			}
    }
}
