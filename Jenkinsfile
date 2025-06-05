pipeline
{
agent any
tools
{
maven 'Maven'
jdk 'JDK'
}
stages
{
stage('Checkout')
{
steps
{
git branch:'master', url:''
}
}
stage('Build')
{
steps
{
sh 'mvn clean package'
}
}
stage('Test')
{
steps
{
sh 'mvn test'
}
}
stage('Run Application')
{
java -jar target/MyMavenApp001-1.0 SNAPSHOT.jar
}
}
post
{
success
{
echo 'BUILD SUCCESSFUL'
}
failure
{
echo 'BUILD FAILURE'
}
}
}
