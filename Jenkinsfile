 pipeline { 
  agent any 
  triggers { 
    pollSCM('* * * * *') 
  } 
  stages { 
Jenkins-practice.md
    stage('Checkout') { 
      steps { 
        git 
branch: 'main',  
        url: '<URL>' 
      } 
    } 
    stage('Build') { 
      steps { 
        sh 
'<MAVEN_BUILD_COMMAND>' 
      } 
    } 
    stage('Test') { 
      steps { 
        sh 
'<MAVEN_TEST_COMMAND>' 
      } 
    } 
    stage('Deploy') { 
      steps { 
        deploy adapters: [tomcat9(credentialsId: '<NAME>', url: '<URL>')], 
contextPath: null, war: 'path/to/war' 
      } 
    } 
  } 
} 
