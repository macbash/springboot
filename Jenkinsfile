node {
    stage('Checkout') {
    checkout scm
}
stage('Deploy') {
sh "git clean -f && git reset --hard origin/master"

if(env.BRANCH_NAME == 'master'){
 sh "mvn deploy -X scm:tag -Drevision=$BUILD_NUMBER-RELEASE"
} else {

 sh "mvn deploy -X -Drevision=$BUILD_NUMBER-SNAPSHOT"

}

}

}
