
properties([pipelineTriggers([githubPush()])])
node('linux') 
{   stage(' Unit Tests') 
 { 
  git 'https://github.com/ilaunchpad/java-project.git'
   sh 'ant -f test.xml -v'
    
   junit 'reports/result.xml'
    
 }   
 stage('Build')
 {   
  
   sh'ant -f build.xml -v'  
   }   
 stage('Deploy') 
 {    
  
  //sh 'aws s3 cp /workspace/java-pipeline/dist/rectangle-${BUILD_NUMBER}.jar s3://samir-assignment-10'
   sh 'aws s3 cp /workspace/my-java-project/dist/*.jar s3://samir-assignment-10/'
  
 }
 stage('Report'){
   withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '1051efa0-9917-41c7-8bd0-d379527fb3d5', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])
  {
   sh'awscloudformationdescribe-stack-resources --region us-east-1 --stack-name jenkins-stack'  
 } 
}
}
