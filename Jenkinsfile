 pipeline { 
  agent any 
  triggers { 
    pollSCM('* * * * *') 
  } 
  stages { 
    stage('Checkout') { 
      steps { 
        git branch: 'main',  
        url: 'https://github.com/naseulgi97/test-1.git' 
      } 
    } 
    stage('Build') { 
      steps { 
        sh 'echo "This is Build step"'
      } 
    } 
    stage('Test') { 
      steps { 
        sh 'echo "This is Test step"'
      } 
    } 
    stage('Deploy') { 
      steps { 
        deploy adapters: [tomcat9(credentialsId: 'tomcat-manager', url: 'http://192.168.56.102:8080/')], contextPath: null, war: 'target/hello-world.war' 
      } 
    } 
  } 
} 