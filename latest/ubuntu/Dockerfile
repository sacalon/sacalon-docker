FROM ubuntu:latest

# set /usr/local/bin to PATH
ENV PATH /usr/local/bin:$PATH

# set LANG to en_US.UTF-8
ENV LANG en_US.UTF-8

# update and install base pacakges
RUN apt update; \
    apt install -y build-essential \
    git \
    python3 \
    python3-pip \
    curl \
    libssl-dev \
    libcrypt-dev

# install pip packages
RUN pip install -U pip \
    setuptools \
    wheel \
    pyinstaller

# clone and build the hascal
RUN git clone https://github.com/hascal/hascal.git /usr/local/src/hascal; \
    cd /usr/local/src/hascal; \
    pip install -r requirements.txt; \
    make build  # this will build the hascal executable

# install hascal
RUN cp -v /usr/local/src/hascal/dist/hascal /usr/local/bin/hascal; \
    chmod +x /usr/local/bin/hascal; \
    cp -rv /usr/local/src/hascal/dist/hlib /usr/local/lib/hascal;

# show hascal version
RUN hascal
