node {
    stage('Checkout') {
    checkout scm
}
stage('Deploy') {
sh "git clean -f && git reset --hard origin/master"

if(env.BRANCH_NAME == 'master'){
 sh "mvn deploy scm:tag -Drevision=$BUILD_NUMBER-RELEASE"
} else {
def pom = readMavenPom file: 'pom.xml'
def version = pom.version.replace("\${revision}", "2-SNAPSHOT")
println version
pom.version = version
writeMavenPom model: pom

 sh "mvn deploy "
}

}

}
