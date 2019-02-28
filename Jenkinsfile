node {
   stage ('checkout repository') {
      // get our rep cloned and prepped for action
      deleteDir()
      checkout scm
   }

   stage ('Render configurations') {
     // Generate our configurations with our playbooks
   }

   stage ('Unit Testing') {
     //Do some kind of "linting" on code to make sure nothing is screwed up
   }


   stage ('Deploy Configurations to Dev') {
     // Push the configurations out to the dev environment
   }


   stage ('Functional Integration Testing') {
     // ping stuff to check dev
   }


   stage ('Promote Configurations to Production') {
     // ping stuff to check dev
   }

   stage ('Production Functional/Integration Testing') {
    // ping stuff to check prod
   }


}
