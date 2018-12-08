
properties([pipelineTriggers([githubPush()])])
node('linux') 
{   stage(' Unit Tests') 
 { 
   sh 'ant -f test.xml -v'
    
   junit 'reports/result.xml'
    
 }   
 stage('Build')
 {   
  
   //sh'ant -f build.xml -v'  
   }   
 stage('Deploy') 
 {    
  // sh 'aws cp /workpspace/java-pipeline/dist/*.jar s3://seid665hw10/'
  
 }
 stage('Report'){
  // withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '14dd1bff-3295-4649-a919-3fc6ad57f627', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])
  //{    sh'awscloudformationdescribe-stack-resources --region us-east-1 --stack-name jenkins'  
 } 
}
