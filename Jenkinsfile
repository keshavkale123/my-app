pipeline {
   agent {
    label {
	    label "built-in"
		customWorkspace "/mnt/keshav/"
		}
	}
	stages {
	 stage ('cloning') {
	 steps {
	 cleanWs ()
	     sh "git clone https://github.com/keshavkale123/my-app.git"
	     sh "cp -r /mnt/keshav/my-app/index.html /var/www/html/"
	     sh "chmod -R 777 /var/www/html/"
          }
        }
	stage ('slave-1 clone') {
       steps {
         dir ('/mnt/a1') {
	     cleanWs () 
	     sh "git clone https://github.com/keshavkale123/my-app.git -b a1"
	     sh "chmod -R 777 /mnt/a1/my-app/dev.html" 
	 }
	 }
	}
	stage ('slave-1 deploy') {
	   steps {
         sh "scp -i /mnt/ohio123.pem /mnt/a1/my-app/dev.html ec2-user@172.31.23.77:/var/www/html/" 	
	}
	}
  /*	stage ('slave-2 clone') {
	  steps {
	     dir ('/mnt/a2') {
		 cleanWs ()
		 sh "git clone https://github.com/keshavkale123/my-app.git -b a2"
		 sh "chmod -R 777 /mnt/a2/my-app/qa.html"
		 }
		}
      }
    stage ('slave-2 deploy') {
      steps {
        sh "scp -i /mnt/ohio123.pem /mnt/a2/my-app/qa.html  ec2-user@172.31.23.77:/var/www/html/"
          }
        } */
     }
   }	 
	

	 
