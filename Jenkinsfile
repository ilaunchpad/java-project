
properties([pipelineTriggers([githubPush()])])
node('linux') 
{   stage(' Unit Tests') 
 { 
   sh 'ant -f test.xml -v'
   //junit 'reports/result.xml'
    
 }   
 stage('Build')
 {   
  
   //sh'ant -f build.xml -v'  
   }   
 stage('Deploy') 
 {    
  // sh 'aws cp /workpspace/java-pipeline/dist/*.jar s3://seid665hw10/'
 }
}
