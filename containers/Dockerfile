FROM centos:7

LABEL author="Fredrik Boulund"\
      maintainer="fredrik.boulund@ki.se"

WORKDIR /BACTpipe

RUN yum update -y && \
    yum install -y wget vmstat bzip2 gzip less && \
	wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh && \
	bash Miniconda3-latest-Linux-x86_64.sh -b -p conda && \
	rm Miniconda3-latest-Linux-x86_64.sh && \
	export PATH=/BACTpipe/conda/bin:$PATH && \
	conda update -y --all && \
	conda config --add channels conda-forge && \
    conda config --add channels bioconda && \
	conda install bbmap mash fastqc prokka multiqc shovill && \
	conda update -y openjdk tbl2asn && \
	conda clean --all --yes && \
	yum remove -y wget && \
	yum clean -y all 

ENV PATH /BACTpipe/conda/bin:$PATH
ENV LANG en_US.UTF-8
