pipeline {
   agent any
   stages {
      stage("build") {


        when {
            expression {

                BRANCH_NAME == 'Dev' && CODE_CHANGES == true
            }     
        
        }

       steps {

        echo 'This is build stage'

       }
        
      }    

      stage("testing") {

        when {
            expression {

                BRANCH_NAME == 'Dev'
            }     
        
        }

        steps {

        echo 'This is testing stage'

       }
      } 


       stage("Deployment") {

       steps {

        echo 'This is Deployment stage'

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
