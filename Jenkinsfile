// CODE_CHANGES = getGitChanges() //groovy scripts to check changes
pipeline {
    /* insert Declarative Pipeline here */
  agent any

  environment { //define own environment variabls, it will be available for all stages in this file
      //got to url for predefined variables http://localhost:8080/env-vars.html/

      NEW_VERSION = '1.0.1'
  }

  stages {
    stage("build") { 
        // when { //conditions
        //     expression {
        //         BRANCH_NAME = 'main' && CODE_CHANGES ==true
        //     }
        // }
        steps { //it will execute if the when condition is true
          echo 'building the application...'
          echo "building version ${NEW_VERSION}"
          sh "g++ src/main.cpp -o main1" 
        }
    }
    stage("test") {
        // when { //conditions
        //     expression {
        //         BRANCH_NAME = 'main' || BRANCH_NAME = 'master'
        //     }
        // }
        steps { //it will execute if the when condition is true
          echo 'testing the application...'
          sh "./main1"
        }
    }
    stage("deploy") {
        steps {
          echo 'deploying the application...'
        }
    }

    // //Build status and Build status change
    // post {  //it will execute after all stages executed
    //   always {
    //     //it will be executed always, no matter build failed or success
    //     //sending an email to team for failed or success status
    //   }
    //   success {
    //     //it will run if the build success
    //   }
    //   failure {
    //     //it will run if the build failure
    //   }
    // }
  }
}