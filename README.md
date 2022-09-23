<?xml version="1.0" encoding="UTF-8"?>

<!--
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
-->
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd">
  <pluginGroups>
    <pluginGroup>org.sonarsource.scanner.maven</pluginGroup>
  </pluginGroups>
  <proxies>
  </proxies>
  <servers>
    <server>
      <id>nexusdeploymentrepo</id>
      <username>admin</username>  <!-- Provide Your Nexus Repository Server Username and Password -->
      <password>admin</password>
    </server>

  </servers>
  <mirrors>
  </mirrors>
  <profiles>
    <!--Apache Tomcat Deployment Server Environment Profile Start-->
    <profile>
      <id>env-dev</id>

      <activation>
        <property>
          <name>target-env</name>
          <value>dev</value>
        </property>
      </activation>

      <properties>
        <tomcatPath>/path/to/tomcat/instance</tomcatPath>
      </properties>
    </profile>
  <!--Apache Tomcat Deployment Server Environment Profile End-->
	<!--Nexus Repository Manager's Profile Start-->
	<profile>
     <id>snapshot</id>
     <repositories>
       <repository>
         <id>nexus-snapshot-repo</id>
         <name>your custom repo</name>
         <url>http://54.152.101.121:8081/repository/maven-snapshots/</url>
       </repository>
	   
     </repositories>
   </profile>
    <profile>
     <id>release</id>
     <repositories>
       <repository>
         <id>nexus-release-repo</id>
         <name>your custom repo</name>
         <url>http://54.152.101.121:8081/repository/maven-release/</url>
       </repository>
     </repositories>
   </profile>
   <!--Nexus Repository Manager's Profile End-->
   <!--SonarQube/Sonar Profile-->
   <profile>
      <id>sonar</id>
      <activation>
        <activeByDefault>true</activeByDefault>
      </activation>
      <properties>
        <sonar.host.url>http://44.203.4.255:9000</sonar.host.url>
      </properties>
    </profile>
    <!--End SonarQube/Sonar Profile-->
  </profiles>
</settings>
