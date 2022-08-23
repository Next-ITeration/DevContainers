#######################################################################################
##     The Base image with usable tools
#######################################################################################

FROM registry.access.redhat.com/ubi8/ubi-minimal:latest as OSBASE

LABEL maintainer="Alejandro Medici <alejandro.medici@bnextiteration.com.ar>" \
      name="nit-nodejs-dev-container" \
      author="NiT Team" \
      vendor="NiT" \
      release="0.1.0" \
      summary="NiT Dev Environment containers" \
      description="Defined the proper setup to be used with Visual Studio Code per NodeJS"

RUN microdnf update && \
    microdnf -y install wget && \
    microdnf clean all && rm -rf /var/cache/microdnf

#installing nodejs 
RUN echo "** Installing NodeJS LTS"
#RUN yum install -y gcc-c++ make 
RUN curl -sL https://rpm.nodesource.com/setup_16.x | bash -
RUN microdnf install -y nodejs

COPY ./ /scripts

WORKDIR /scripts

CMD ["/bin/bash"]