FROM biocontainers/biocontainers:v1.0.0_cv4
MAINTAINER biocontainers <biodocker@gmail.com>
LABEL    software="affymetrix-power-tools" \ 
    container="affymetrix-power-tools" \ 
    about.summary="Affymetrix Power Tools (APT) - command-line programs for analyzing microarray data" \ 
    about.home="https://www.thermofisher.com/order/catalog/product/902163" \ 
    software.version="2.12.0" \ 
    version="1" \ 
    about.copyright="Life Technologies Corporation (on behalf of Affymetrix, Inc.). Unpublished rights reserved under the copyright laws of the United States." \ 
    about.license="Custom: Life Technologies End User License Agreement" \ 
    about.license_file="/home/biodocker/EULA.docx" \ 
    about.tags="genomics microarray affymetrix APT"

USER biodocker

WORKDIR /tmp
RUN wget https://downloads.thermofisher.com/APT/APT_2.12.0/apt_2.12.0_linux_64_x86_binaries.zip && unzip /tmp/apt_2.12.0_linux_64_x86_binaries.zip -d ./ \
  && mv /tmp/bin/* /home/biodocker/bin/ \
  && mv /tmp/EULA.docx /home/biodocker/EULA.docx \
  && chmod -R 755 /home/biodocker/bin/ \
  && rm -rf /tmp/*

ENV PATH /home/biodocker/bin/apt:$PATH

VOLUME ["/data"]

WORKDIR /data/

CMD ["/bin/bash"]