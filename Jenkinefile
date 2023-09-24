pipeline {
	agent {
		label {
			label "built-in"
			 customWorkspace "/mnt/keshav/"
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
			  sh " cp -r /mnt/keshav/my-app/index.html /var/www/html/"
		      sh " chmod -R 777 /var/www/html "
			  }
			}
			 stage ('branch a1') {
			 agent {
		label {
			label "built-in"
			 customWorkspace "/mnt/keshav1/"
			 }
			}
			steps { 
               cleanWs ()			
			  sh "git clone https://github.com/keshavkale123/my-app.git -b a1"
			  sh " cp -r /mnt/keshav1/my-app/dev.html /var/www/html/"
		      sh " chmod -R 777 /var/www/html "
			  }
	              }      
        }
    }		
