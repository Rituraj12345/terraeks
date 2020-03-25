pipeline {
    agent any

    stages {
        stage('install terraform') {
            steps {
	      sh 'sudo rm -rf /home/ec2-user/new'
              sh 'sudo mkdir /home/ec2-user/new'
              sh 'sudo cd /home/ec2-user/new'
	      sh 'sudo rm -rf /var/lib/jenkins/workspace/eks/terraform'
	      sh 'sudo rm -rf /var/lib/jenkins/workspace/eks/terraform_0.12.23_linux_amd64.zip'
              sh 'sudo wget https://releases.hashicorp.com/terraform/0.12.23/terraform_0.12.23_linux_amd64.zip'
              sh 'sudo yum install unzip -y'
	      echo 'unzip installed'
              sh 'sudo unzip terraform_0.12.23_linux_amd64.zip'
	      sh  'sudo cp ./terraform /usr/bin/terraform && export PATH=$PATH:/usr/bin'
	      sh 'terraform --version'
              //sh 'sudo echo $"export PATH=\$PATH:$(pwd)" >> ~/.bash_profile'
              //sh 'source ~/.bash_profile'
              echo 'terraform done'
		    		}
        	}
	/*stage('install kubectl') {
            steps {
              sh  'sudo curl -o kubectl https://amazon-eks.s3-us-west-2.amazonaws.com/1.14.6/2019-08-22/bin/linux/amd64/kubectl'
	         	  sh  'sudo curl -o kubectl.sha256 https://amazon-eks.s3-us-west-2.amazonaws.com/1.14.6/2019-08-22/bin/linux/amd64/kubectl.sha256'
              sh  'sudo openssl sha1 -sha256 kubectl'
              sh  'sudo chmod +x ./kubectl'
              sh  'sudo cp ./kubectl /usr/bin/kubectl && export PATH=$PATH:/usr/bin'
              sh  'echo "export PATH=$PATH:/usr/bin" >> ~/.bashrc'
	      sh  'echo "export PATH=$PATH:/usr/bin" >> ~/.bash_profile'
	      sh  'source ~/.bashrc'
	      sh  'source ~/.bash_profile'
              sh  'sudo kubectl version --short --client'
              sh  'sudo rm -rf ~/.kube && sudo mkdir ~/.kube'                                 
              sh  'sudo touch ~/.kube/config-eks'
              echo 'kubectl done'
		    		}
        	}
	stage('install iam-auth') {
            steps {
              sh  'sudo curl -o aws-iam-authenticator https://amazon-eks.s3-us-west-2.amazonaws.com/1.14.6/2019-08-22/bin/linux/amd64/aws-iam-authenticator'
	      sh  'sudo chmod +x ./aws-iam-authenticator'
	      sh  'sudo cp ./aws-iam-authenticator /usr/bin/aws-iam-authenticator && export PATH=$PATH:/usr/bin'
	      echo 'iam done'
	      sh 'aws-iam-authenticator version'
	 			   }
		}
	 stage('create cluster') {
            steps {
	      sh 'sudo rm -rf terraform-script-eks /home/ec2-user/terra'
	      sh 'sudo rm -rf *;git clone https://github.com/samreenimran/terraform-script-eks.git /home/ec2-user/terra'
	      //sh 'cd /var/lib/jenkins/workspace/eks/terraform-script-eks'
	     // sh 'sudo ls -al'
	      sh 'sudo /home/ec2-user/terra/terraform init /home/ec2-user/terra'
	      sh 'sudo /home/ec2-user/terra/terraform fmt /home/ec2-user/terra'
	      sh 'sudo /home/ec2-user/terra/terraform validate /home/ec2-user/terra'
	      sh 'sudo ls /home/ec2-user/terra; sudo ~/terra/terraform plan /home/ec2-user/terra'
	      sh 'sudo /home/ec2-user/terra/terraform apply --auto-approve /home/ec2-user/terra'
		
	    }
	 }*/
    }
}
