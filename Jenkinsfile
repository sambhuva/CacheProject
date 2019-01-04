node () {
  
   if  (env.BRANCH_NAME == 'master') {
       checkout()
       echo "checkout for branch==============================================-------------------"+env.BRANCH_NAME   
      build()
               
    } 
    else {
       echo "checkout for branch==============================================-------------------"+env.BRANCH_NAME  
  echo "this other branch"
    }
}

def checkout(){
 stage 'Checkout code'
    context="continuous-integration/jenkins/"
    context +="branch/checkout"
    checkout scm
}

def build(){
 stage ('Build') {
  echo "starting building==========================================================-------------"
   
 
      bat "mvn clean install -DskipTests=true -Dmaven.javadoc.skip=true -Dcheckstyle.skip=true -B -V"
 
    
  }
}
