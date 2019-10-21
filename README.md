# nexusinstallation
prerequisites
create a t2.medium instance 
install jre (jdk)

     cd /opt
     #get url from sona nexus official site https://help.sonatype.com/repomanager3/download
     sudo wget https://download.sonatype.com/nexus/3/latest-unix.tar.gz
     sudo tar -xf latest-unix.tar.gz
     sudo chown -R ec2-user:ec2-user sonatype-work/ nexus-3.19.1-01/
     sudo mv nexus-3.19.1-01/ nexus3
     cd nexus3/bin
     sudo vi nexus.rc -> run as useer ="ec2-user"
     sudo ln -s /opt/nexus3/bin/nexus /etc/init.d/nexus
     cd /etc/init.d
     sudo chkconfig --add nexus
     sudo chkconfig nexus on
     sudo service nexus start
     sudo service status
     sudo service nexus status

working with nexus from build/jenkins server

    sudo vi /etc/docker/daemon.json
    
    where daemon.json is
    {
        "insecure-registries":["3.14.245.92:8083"],
        "disable-legacy-registry":true
     }
    
    here 3.14.245.92 is the public ip of nexus server and its port 8081 is the default port of nexus 
    and 8083 is the repository port of http.

    sudo service docker restart
    sudo docker login -u admin -p sowdha1965 3.14.245.92:8083
