pipeline{
    agent any
    stages{
        stage ("Checkout"){
            steps{
        git branch:"main", url:"https://github.com/KostadinDermendzhiev/course3-jenkins-gs-spring-petclinic.git"
    }
        }
    stage ("Build"){
        steps{
        sh "./mvnw package"
    }
    }
    stage ("Capture"){
        steps{
        archiveArtifacts artifacts: '**/target/*.jar'
        jacoco()
        junit stdioRetention: '', testResults: '**/target/surefire-reports/TEST*.xml'
    }
    }

}
}
