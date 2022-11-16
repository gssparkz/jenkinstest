pipeline {
   agent any
   stages {
      stage("build") {


        when {
            expression {

                BRANCH_NAME == 'dev' && CODE_CHANGES == true
            }     
        
        }

       steps {

        echo 'This is build stage'

       }
        
      }    

      stage("testing") {

        when {
            expression {

                BRANCH_NAME == 'dev'
            }     
        
        }

        steps {

        echo 'This is build stage'

       }
      } 


       stage("Deployment") {

       steps {

        echo 'This is build stage'

       }
      } 

   }

   post {
     

     always {

        // send email about condition
        echo 'sent an email to the group'
     }


     success {
         echo 'this is successfully completed'

     }

   }

}   
