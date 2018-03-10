FROM centos:7
MAINTAINER Eswarmoorthi Duraisamy <eswar2k11@gmail.com>
RUN yum clean all && \
    yum -y install epel-release && \
	yum install openssh-server openssh-clients && \
	yum install -y nginx
EXPOSE 80 443 22
ENTRYPOINT ["/usr/sbin/nginx","-g","daemon off;"]
