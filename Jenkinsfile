pipeline
{

agent {
  label 'DevServer'
}

tools {
  maven 'mymaven'
}

stages{

    stage('build')
    {
        steps {
            sh 'mvn clean package'
        }

        post {
        success {
             dir("webapp/target/")
            {
            stash name: "maven-build", includes: "*.war"
                 }
                 }
            }

    }

<<<<<<< HEAD
=======
<<<<<<<<< Temporary merge branch 1
    stage('deploy_dev')
    {
        when { expression {params.select_environment == 'dev'}
        beforeAgent true}
        agent { label 'DevServer' }
        steps
        {
            dir("/var/www/html")
            {
                unstash "maven-build"
            }
            sh """
            cd /var/www/html/
            jar -xvf webapp.war
            """
        }
    }

    stage('deploy_prod')
    {
      when { expression {params.select_environment == 'prod'}
        beforeAgent true}
        agent { label 'ProdServer' }
        steps
        {
             timeout(time:5, unit:'DAYS'){
                input message: 'Deployment approved?'
             }
            dir("/var/www/html")
            {
                unstash "maven-build"
            }
            sh """
            cd /var/www/html/
            jar -xvf webapp.war
            """
        }  
    }

=========
>>>>>>>>> Temporary merge branch 2
   

    
}

}
>>>>>>> 2c9b78c7c28fb91a93d61c60b5596ea60fdd6398
