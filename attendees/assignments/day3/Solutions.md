Assignment1:

-> Pre requisite

Install below plugins
Maven integration plugin
Checkstyle Plug-in
FindBugs Plug-in
Static Analysis Collector Plug-in
Cobertura Plugin
Install below softwares under Global tool configuration
Maven | Maven 3.5.2

Java | You need Oracle account for same | JDK 8u162

Git | You need to manually install git first

apt-get -y install git


Solution 1: Installed all  the prerequisite plugins in jenkins successfullyy

-> Setup CodeStability Job

Choose Job type as MavenProject
Provide git repository https://github.com/OpsTree/ContinuousIntegration
Use clean compile as target

Solution : Created job as maven project and provide mentioned git repository link in jenkins git plugin.

Setup pom file path : Spring3hibernate/pom.xml

Select Goal : Clean Compile.
Start the build job and completed successfully.
Checked on the target location on jenkins server Spring3Hibernate.war file created.

-> Setup static code analysis Job

Choose Job type as MavenProject
Provide git repository https://github.com/OpsTree/ContinuousIntegration
Use clean compile findbugs:findbugs checkstyle:checkstyle as target

Solution : Created job as maven project and provide mentioned git repository link in jenkins git plugin.

Setup pom file path : Spring3hibernate/pom.xml

Select Goal : clean compile findbugs:findbugs checkstyle:checkstyle.
Start the build job and completed successfully.
Checked  BugInstance size is 7
[INFO] Error size is 0
[INFO] Total bugs: 7.

-> Setup code coverage Job

Choose Job type as MavenProject
Provide git repository https://github.com/OpsTree/ContinuousIntegration
Use clean compile cobertura:cobertura as target


Solution : Created job as maven project and provide mentioned git repository link in jenkins git plugin.

Setup pom file path : Spring3hibernate/pom.xml

Select Goal :  clean compile cobertura:cobertura.
Start the build job and completed successfully.

Cobertura: Loaded information on 15 classes.
Report time: 456ms

[INFO] Cobertura Report generation was successful.

