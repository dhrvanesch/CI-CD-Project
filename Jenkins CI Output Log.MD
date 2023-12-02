~~~~
Started by user admin
Running as SYSTEM
Building in workspace /var/lib/jenkins/workspace/App_CI_Job
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/App_CI_Job/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/dhrvanesch/Java-App.git # timeout=10
Fetching upstream changes from https://github.com/dhrvanesch/Java-App.git
 > git --version # timeout=10
 > git --version # 'git version 2.40.1'
 > git fetch --tags --force --progress -- https://github.com/dhrvanesch/Java-App.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision 1ea81f11eda5f491fc811e4cdad08c17c881a763 (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 1ea81f11eda5f491fc811e4cdad08c17c881a763 # timeout=10
Commit message: "Merge branch 'main' of https://github.com/dhrvanesch/Java-App"
 > git rev-list --no-walk 1ea81f11eda5f491fc811e4cdad08c17c881a763 # timeout=10
Parsing POMs
Established TCP socket on 37759
[App_CI_Job] $ /usr/lib/jvm/java-11-openjdk-11.0.20.0.8-1.amzn2.0.1.x86_64/bin/java -cp /var/lib/jenkins/plugins/maven-plugin/WEB-INF/lib/maven35-agent-1.14.jar:/opt/maven/boot/plexus-classworlds-2.7.0.jar:/opt/maven/conf/logging jenkins.maven3.agent.Maven35Main /opt/maven /var/lib/jenkins/%C/jenkins/war/WEB-INF/lib/remoting-3160.vd76b_9ddd10cc.jar /var/lib/jenkins/plugins/maven-plugin/WEB-INF/lib/maven35-interceptor-1.14.jar /var/lib/jenkins/plugins/maven-plugin/WEB-INF/lib/maven3-interceptor-commons-1.14.jar 37759
<===[JENKINS REMOTING CAPACITY]===>channel started
Executing Maven:  -B -f /var/lib/jenkins/workspace/App_CI_Job/pom.xml clean install
[INFO] Scanning for projects...
[WARNING] 
[WARNING] Some problems were encountered while building the effective model for com.example.maven-project:server:jar:1.0-SNAPSHOT
[WARNING] Reporting configuration should be done in <reporting> section, not in maven-site-plugin <configuration> as reportPlugins parameter.
[WARNING] 
[WARNING] Some problems were encountered while building the effective model for com.example.maven-project:webapp:war:1.0-SNAPSHOT
[WARNING] Reporting configuration should be done in <reporting> section, not in maven-site-plugin <configuration> as reportPlugins parameter.
[WARNING] 
[WARNING] Some problems were encountered while building the effective model for com.example.maven-project:maven-project:pom:1.0-SNAPSHOT
[WARNING] Reporting configuration should be done in <reporting> section, not in maven-site-plugin <configuration> as reportPlugins parameter. @ line 58, column 24
[WARNING] 
[WARNING] It is highly recommended to fix these problems because they threaten the stability of your build.
[WARNING] 
[WARNING] For this reason, future Maven versions might no longer support building such malformed projects.
[WARNING] 
[WARNING] The project com.example.maven-project:maven-project:pom:1.0-SNAPSHOT uses prerequisites which is only intended for maven-plugin projects but not for non maven-plugin projects. For such purposes you should use the maven-enforcer-plugin. See https://maven.apache.org/enforcer/enforcer-rules/requireMavenVersion.html
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Build Order:
[INFO] 
[INFO] Maven Project                                                      [pom]
[INFO] Server                                                             [jar]
[INFO] Webapp                                                             [war]
[INFO] 
[INFO] --------------< com.example.maven-project:maven-project >---------------
[INFO] Building Maven Project 1.0-SNAPSHOT                                [1/3]
[INFO]   from pom.xml
[INFO] --------------------------------[ pom ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ maven-project ---
[INFO] 
[INFO] --- install:3.1.1:install (default-install) @ maven-project ---
[INFO] Installing /var/lib/jenkins/workspace/App_CI_Job/pom.xml to /var/lib/jenkins/.m2/repository/com/example/maven-project/maven-project/1.0-SNAPSHOT/maven-project-1.0-SNAPSHOT.pom
[INFO] 
[INFO] ------------------< com.example.maven-project:server >------------------
[INFO] Building Server 1.0-SNAPSHOT                                       [2/3]
[INFO]   from server/pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ server ---
[INFO] Deleting /var/lib/jenkins/workspace/App_CI_Job/server/target
[INFO] 
[INFO] --- resources:2.5:resources (default-resources) @ server ---
[debug] execute contextualize
[INFO] Using 'utf-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory /var/lib/jenkins/workspace/App_CI_Job/server/src/main/resources
[INFO] 
[INFO] --- compiler:2.3.2:compile (default-compile) @ server ---
[INFO] Compiling 1 source file to /var/lib/jenkins/workspace/App_CI_Job/server/target/classes
[INFO] 
[INFO] --- resources:2.5:testResources (default-testResources) @ server ---
[debug] execute contextualize
[INFO] Using 'utf-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory /var/lib/jenkins/workspace/App_CI_Job/server/src/test/resources
[INFO] 
[INFO] --- compiler:2.3.2:testCompile (default-testCompile) @ server ---
[INFO] Compiling 1 source file to /var/lib/jenkins/workspace/App_CI_Job/server/target/test-classes
[INFO] 
[INFO] --- surefire:2.11:test (default-test) @ server ---
[INFO] Surefire report directory: /var/lib/jenkins/workspace/App_CI_Job/server/target/surefire-reports

-------------------------------------------------------
 T E S T S
-------------------------------------------------------
Running com.example.TestGreeter
Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.073 sec

Results :

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0

[JENKINS] Recording test results
[INFO] 
[INFO] --- jar:3.3.0:jar (default-jar) @ server ---
[INFO] Building jar: /var/lib/jenkins/workspace/App_CI_Job/server/target/server.jar
[INFO] 
[INFO] --- install:3.1.1:install (default-install) @ server ---
[INFO] Installing /var/lib/jenkins/workspace/App_CI_Job/server/pom.xml to /var/lib/jenkins/.m2/repository/com/example/maven-project/server/1.0-SNAPSHOT/server-1.0-SNAPSHOT.pom
[INFO] Installing /var/lib/jenkins/workspace/App_CI_Job/server/target/server.jar to /var/lib/jenkins/.m2/repository/com/example/maven-project/server/1.0-SNAPSHOT/server-1.0-SNAPSHOT.jar
[INFO] 
[INFO] ------------------< com.example.maven-project:webapp >------------------
[INFO] Building Webapp 1.0-SNAPSHOT                                       [3/3]
[INFO]   from webapp/pom.xml
[INFO] --------------------------------[ war ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ webapp ---
[INFO] Deleting /var/lib/jenkins/workspace/App_CI_Job/webapp/target
[INFO] 
[INFO] --- resources:2.5:resources (default-resources) @ webapp ---
[debug] execute contextualize
[INFO] Using 'utf-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory /var/lib/jenkins/workspace/App_CI_Job/webapp/src/main/resources
[INFO] 
[INFO] --- compiler:2.3.2:compile (default-compile) @ webapp ---
[INFO] No sources to compile
[INFO] 
[INFO] --- resources:2.5:testResources (default-testResources) @ webapp ---
[debug] execute contextualize
[INFO] Using 'utf-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory /var/lib/jenkins/workspace/App_CI_Job/webapp/src/test/resources
[INFO] 
[INFO] --- compiler:2.3.2:testCompile (default-testCompile) @ webapp ---
[INFO] No sources to compile
[INFO] 
[INFO] --- surefire:2.11:test (default-test) @ webapp ---
[INFO] No tests to run.
[INFO] Surefire report directory: /var/lib/jenkins/workspace/App_CI_Job/webapp/target/surefire-reports

-------------------------------------------------------
 T E S T S
-------------------------------------------------------

Results :

Tests run: 0, Failures: 0, Errors: 0, Skipped: 0

[JENKINS] Recording test results
[INFO] 
[INFO] --- war:3.3.2:war (default-war) @ webapp ---
[INFO] Packaging webapp
[INFO] Assembling webapp [webapp] in [/var/lib/jenkins/workspace/App_CI_Job/webapp/target/webapp]
[INFO] Processing war project
[INFO] Copying webapp resources [/var/lib/jenkins/workspace/App_CI_Job/webapp/src/main/webapp]
[INFO] Building war: /var/lib/jenkins/workspace/App_CI_Job/webapp/target/webapp.war
[INFO] 
[INFO] --- install:3.1.1:install (default-install) @ webapp ---
[INFO] Installing /var/lib/jenkins/workspace/App_CI_Job/webapp/pom.xml to /var/lib/jenkins/.m2/repository/com/example/maven-project/webapp/1.0-SNAPSHOT/webapp-1.0-SNAPSHOT.pom
[INFO] Installing /var/lib/jenkins/workspace/App_CI_Job/webapp/target/webapp.war to /var/lib/jenkins/.m2/repository/com/example/maven-project/webapp/1.0-SNAPSHOT/webapp-1.0-SNAPSHOT.war
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for Maven Project 1.0-SNAPSHOT:
[INFO] 
[INFO] Maven Project ...................................... SUCCESS [  1.096 s]
[INFO] Server ............................................. SUCCESS [  4.694 s]
[INFO] Webapp ............................................. SUCCESS [  1.826 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  9.945 s
[INFO] Finished at: 2023-12-01T18:39:40Z
[INFO] ------------------------------------------------------------------------
[JENKINS] Archiving /var/lib/jenkins/workspace/App_CI_Job/webapp/pom.xml to com.example.maven-project/webapp/1.0-SNAPSHOT/webapp-1.0-SNAPSHOT.pom
[JENKINS] Archiving /var/lib/jenkins/workspace/App_CI_Job/webapp/target/webapp.war to com.example.maven-project/webapp/1.0-SNAPSHOT/webapp-1.0-SNAPSHOT.war
[JENKINS] Archiving /var/lib/jenkins/workspace/App_CI_Job/server/pom.xml to com.example.maven-project/server/1.0-SNAPSHOT/server-1.0-SNAPSHOT.pom
[JENKINS] Archiving /var/lib/jenkins/workspace/App_CI_Job/server/target/server.jar to com.example.maven-project/server/1.0-SNAPSHOT/server-1.0-SNAPSHOT.jar
[JENKINS] Archiving /var/lib/jenkins/workspace/App_CI_Job/pom.xml to com.example.maven-project/maven-project/1.0-SNAPSHOT/maven-project-1.0-SNAPSHOT.pom
channel stopped
SSH: Connecting from host [Jenkinsserver]
SSH: Connecting with configuration [ansible-server] ...
SSH: EXEC: completed after 11,609 ms
SSH: Disconnecting configuration [ansible-server] ...
SSH: Transferred 1 file(s)
Triggering a new build of App_CD_Job
Finished: SUCCESS
~~~~
