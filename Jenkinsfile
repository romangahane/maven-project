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

