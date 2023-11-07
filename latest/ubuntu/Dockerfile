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

# clone and build the sacalon
RUN git clone https://github.com/sacalon-lang/sacalon.git /usr/local/src/sacalon; \
    cd /usr/local/src/sacalon; \
    pip install -r requirements.txt; \
    make build  # this will build the sacalon executable

# install sacalon
RUN cp -v /usr/local/src/sacalon/dist/hascal /usr/local/bin/hascal; \
    chmod +x /usr/local/bin/sacalon; \
    cp -rv /usr/local/src/sacalon/dist/hlib /usr/local/lib/hascal;

# show sacalon version
RUN sacalon
