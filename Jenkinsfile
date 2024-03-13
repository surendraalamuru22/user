pipeline {
   agent {
     node { label 'workstation'}
   }
   stages {
     stage ('code quality') {
       steps {
          echo 'code quality'
       }
     }
     stage ('lint checks') {
      when {
          anyOf {
             branch 'main'
             tag "*"
          }
      }
       steps {
           echo 'lint checks'
       }
     }
     stage ('unit tests') {
      when {
         anyOf {
            branch 'main'
            tag "*"
         }
      }
       steps {
          echo 'unit tests'
       }
     }
     stage ('download dependencies') {
         when { tag "*" }
           steps {
               echo 'download dependencies'
           }
     }
     stage ('prepare artifact') {
      when { tag "*" }
       steps {
          echo 'prepare artifact'
       }
     }
     stage ('publish artifact') {
       when { tag "*" }
         steps {
               echo 'publish artifact'
         }
     }
   }
}