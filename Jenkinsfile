pipeline {
   agent any

   parameters {
      choice(name: 'VERSION', choices:['1.0.1', '1.0.2', '1.0.3'], description:'this is to select the version')

   }

    environment {

        NEW_VERSION = '1.1.2'
    }

   stages {
      stage("build") {


        when {
            expression {

                env.BRANCH_NAME == 'Dev' && env.CODE_CHANGES == true
            }     
        
        }

       steps {

        echo 'This is build stage'

       }
        
      }    

      stage("testing") {

        when {
            expression {

                env.BRANCH_NAME == 'Dev'
            }     
        
        }

        steps {

        echo 'This is testing stage'
        echo "code build is ${NEW_VERSION}"

       }
      } 


       stage("Deployment") {

       steps {

        echo 'This is Deployment stage'
        echo "deploying the version ${params.VERSION}"

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
