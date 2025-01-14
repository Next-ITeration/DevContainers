#######################################################################################
##     The Base image with usable tools
#######################################################################################

FROM registry.access.redhat.com/ubi8/ubi-minimal:latest AS osbase

LABEL maintainer="Alejandro Medici <alejandro.medici@bnextiteration.com.ar>" \
      name="nit-python3-dev-container" \
      author="NiT Team" \
      vendor="NiT" \
      release="0.1.0" \
      summary="NiT Dev Environment containers" \
      description="Defined the proper setup to be used with Visual Studio Code for Python3"

RUN microdnf update && \
    microdnf -y install wget tar gzip git && \
    microdnf clean all && rm -rf /var/cache/microdnf

#installing Python
RUN echo "** Installing Python LTS"
RUN INSTALL_PKGS="python311 glibc-langpack-en findutils nss_wrapper" && \
    microdnf -y --setopt=tsflags=nodocs --setopt=install_weak_deps=0 install $INSTALL_PKGS && \
    microdnf -y clean all --enablerepo='*'

RUN curl -sSL https://bootstrap.pypa.io/get-pip.py -o get-pip.py && \
    python get-pip.py

COPY ./ /scripts

WORKDIR /scripts

CMD ["/bin/bash"]
