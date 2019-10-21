# nexusinstallation
prerequisites
create a t2.medium instance 
install jre (jdk)

     cd /opt
     #get url from sona nexus official site https://help.sonatype.com/repomanager3/download
     sudo wget https://download.sonatype.com/nexus/3/latest-unix.tar.gz
     sudo tar -xf latest-unix.tar.gz
     ls
     ls -l
     sudo chown -R ec2-user:ec2-user sonatype-work/ nexus-3.19.1-01/
     ls -l
     sudo mv nexus-3.19.1-01/ nexus3
     cd nexus3
     ls
     cd bin
     sudo vi nexus.rc
     sudo ln -s /opt/nexus3/bin/nexus /etc/init.d/nexus
     cd /etc/init.d
     sudo chkconfig --add nexus
     sudo chkconfig nexus on
     sudo service nexus start
     sudo service status
     sudo service nexus status
