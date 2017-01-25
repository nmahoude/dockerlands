FROM centos:7

MAINTAINER nmahoude@gmail.com

# update and install unzip & jdk
RUN yum update -y
RUN yum -y install unzip
RUN yum -y install java-1.8.0-openjdk-devel
RUN yum clean all

# env setup to make java available
ENV JAVA_HOME /usr/lib/jvm/java-1.8.0
ENV PATH "$PATH":/${JAVA_HOME}/bin:.:

# Define default command.
CMD ["bash"]
