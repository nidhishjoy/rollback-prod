#!groovy


try {


   node ('aws') {
        
        stage('Deployment on DEV') {
            checkout scm

          
  
        sh 'docker-compose -f local-compose.yml build apache'
        sh 'docker-compose -f local-compose.yml  up -d apache'
        echo "Success"   
	}  
        
    }


}



finally {

    node ('aws') {
        stage('Cleanup on testing host') {
            sh 'docker ps'
         }
   }
}
