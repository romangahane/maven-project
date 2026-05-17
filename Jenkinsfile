pipeline
{

agent {
  label 'DevServer'
}

tools {
  maven 'mymeven'
}

stages{

    stage('build')
    {
        steps {
            sh 'mvn clean package'
        }

        post {
        success {
            archiveArtifacts artifacts: '**/target/*.war'
                 }
            }

    }

   

    
}

}
