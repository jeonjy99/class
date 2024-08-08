 pipeline { 
  agent {
    label "jenkins-node"
  }
  stages { 
    stage('Checkout') { 
      steps { 
        git branch: 'main',  
        url: 'https://github.com/jeonjy99/class.git' 
      } 
    } 
    stage('Build') { 
      steps { 
        sh 'mvn clean package' 
      } 
    } 
    stage('Test') { 
      steps { 
        sh 'echo "Hello world"' 
      } 

    } 
    stage('Deploy') { 
      steps { 
        deploy adapters: [tomcat9(credentialsId: 'tomcat-manager', url: 'http://192.168.56.102:8080/')], contextPath: null, war: 'target/hello-world.war' 
      } 
    } 
  } 
}