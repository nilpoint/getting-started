1.Using yum
===========
Login as root
-------------
yum update

yum install -y java

yum install tomcat6 tomcat6-webapps tomcat6-admin-webapps

You can modify default port 8080 to 80 (if required)

vi /usr/share/tomcat6/conf/server.xml

    <Connector port="80" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="8443" />

For tomcat admin modify file

    vi /usr/share/tomcat6/conf/tomcat-users.xml

add line

    <user username="admin" password="tomcatpass" roles="manager"/>

in between

    <tomcat-users> & </tomcat-users>

Add permanent at start-up

    chkconfig tomcat6 on

Start tomcat
------------
service tomcat6 start

Add port on iptables
--------------------
    iptables -I INPUT -p tcp --dport 8o -j ACCEPT
    service iptables save
    service iptables restart

Open browser and add url or ip of your server in address bar click on Tomcat Manager give username and password as you have added on the file tomact-users.xml as admin and tomcatpass.
