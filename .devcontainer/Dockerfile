FROM ubuntu:jammy
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
    apt-get install --no-install-recommends -y \
        apt-utils \
        autoconf \
        automake \
        build-essential \
        ccache \
        cmake \
        cmake-format \
        clang-14 clang-tidy-14 clang-format-14 llvm-14 \
        curl \
        cython3 \
        doxygen \
        ffmpeg \
        gcc-10 g++-10 \
        gdb \
        gfortran \
        git \
        gnupg \
        graphviz \
        jq \
        jupyter-notebook \
        jupyter-nbconvert \
        lcov \
        libblas-dev \
        libboost-dev libboost-serialization-dev libboost-mpi-dev libboost-filesystem-dev libboost-test-dev \
        libdigest-sha-perl \
        libfftw3-dev \
        libfftw3-mpi-dev \
        libgsl-dev \
        libhdf5-openmpi-dev \
        liblapack-dev \
        libopenmpi-dev \
        libthrust-dev \
        libtool \
        nvidia-cuda-toolkit \
        openmpi-bin \
        openssh-client \
        pkg-config \
        python3 \
        pylint \
        python3-autopep8 \
        python3-coverage \
        python3-dev \
        python3-h5py \
        python3-lxml \
        python3-numpy \
        python3-matplotlib \
        python3-pint \
        python3-pip \
        python3-pycodestyle \
        python3-requests  \
        python3-scipy \
        python3-setuptools \
        python3-tqdm \
        python3-venv \
        rsync \
        texlive-base \
        vim && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ENV HOME="/home/mpi_nvt"
ENV PATH="${HOME}/.local/bin${PATH:+:$PATH}"
RUN pip3 install --no-cache --user \
  pre-commit==2.17.0 \
  nbconvert==6.4.5 \
  sphinx==4.5.0 \
  sphinx-toggleprompt==0.2.0 \
  sphinxcontrib-bibtex==2.5.0 \
  numpydoc==1.5.0
WORKDIR /home/mpi_nvt
RUN pip install pandas
RUN pip install jupyterlab

COPY . .
#RUN cd espresso/build/
#RUN cmake ..
#RUN make

#ENV PYTHONPATH="${PYTHONPATH:+$PYTHONPATH:}/workspaces/molecular_dynamics/espresso/build/pypresso"

EXPOSE 8888
