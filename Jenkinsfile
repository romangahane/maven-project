pipeline
{

agent {
  label 'DevServer'
}

tools {
  maven 'mymeven'
}

environment {
    NAME = "Roman"
}
 
parameters {
  string defaultValue: 'Gahane', name: 'LASTNAME '
}

stages{

    stage('build')
    {
        steps {
            sh 'mvn clean package'
            echo "Hello $NAME ${params.LASTNAME}"
        }

        post {
        success {
            archiveArtifacts artifacts: '**/target/*.war'
                 }
            }

    }

   

    
}

}
