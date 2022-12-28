# tomcat-Demo
Spin a EC2 instance and login .

Become a root user

Install Java : yum install java -y

Install tomcat :
cd /opt
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.62/bin/apache-tomcat-9.0.62.tar.gz

tar -xvzf apache-tomcat-9.0.62.tar.gz

mv apache-tomcat-9.0.62 tomcat

rm -rf apache-tomcat-9.0.62.tar.gz

cd tomcat/bin

./shutdown.sh

./startup.sh

chown -R ec2-user:ec2-user tomcat


check your machine on port <public-ip>:8080
  
find / -name context.xml
  
nano /opt/tomcat/conf/context.xml
  
nano /opt/tomcat/webapps/examples/META-INF/context.xml
  
nano /opt/tomcat/webapps/host-manager/META-INF/context.xml
  
nano /opt/tomcat/webapps/manager/META-INF/context.xml
cd ..
  
cd conf/
  
nano tomcat-users.xml

<role rolename="manager-gui"/>
  
<role rolename="manager-script"/>
  
<role rolename="manager-jmx"/>
  
<role rolename="manager-status"/>
  
<user username="tomcat" password="pass123" roles="manager-gui"/>
  
<user username="admin" password="admin123" roles="manager-gui, manager-script, manager-jmx, manager-status"/>

./shutdown.sh
  
./startup.sh ==> Tomcat should be up and running.





