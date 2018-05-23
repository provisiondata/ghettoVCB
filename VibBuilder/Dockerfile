FROM centos:6.6
WORKDIR /root

RUN yum -y install tar openssl python-lxml glibc.i686 git file nss curl libcurl

# Download VIB Author RPM
RUN curl -O http://download3.vmware.com/software/vmw-tools/vibauthor/vmware-esx-vib-author-5.0.0-0.0.847598.i386.rpm
# Install VIB Author
RUN rpm -ivh vmware-esx-vib-author-5.0.0-0.0.847598.i386.rpm
# Download ghettoVCB VIB build script
ADD create_ghettoVCB_vib.sh .
RUN chmod +x create_ghettoVCB_vib.sh
RUN mkdir /artifacts

# Run ghettoVCB VIB build script
RUN create_ghettoVCB_vib.sh

VOLUME ["/artifacts"]

CMD ["/bin/bash"]
