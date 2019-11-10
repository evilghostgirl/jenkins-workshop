node {
    stage ('Hello'){
        echo 'Hello World'
    }
    stage ('Preparation'){
           checkout scm
    }
    stage ('Build') {
        sh 'mvn package'
    }
    stage ('Results') {
       junit '**/target/surefire-reports/TEST-*.xml'
       
    }
    stage ('JavaDoc') {
        sh 'mvn site site:site'
        archiveArtifacts 'target/gildedrose-*.jar'
    }
}

