node{
    stage('SCM Checkout'){
         git 'https://github.com/seenuvasu145/myapp.git'
}
    stage('Compile-Package'){

         def mvnHome = tool name: 'maven_home', type: 'maven' 
         sh "${mvnHome}/bin/mvn package"
	 sh 'cp target/*.war /opt/k8s-lab/myweb-0.0.5.war'maven_home
  } 
    
    stage('Build Docker image'){
        
	  sh 'ansible-playbook /opt/k8s-lab/create-simple-devops-image.yml'
	}
   
}
