FROM rocker/verse:devel
MAINTAINER "Carl Boettiger" cboettig@ropensci.org

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
    lbzip2 \
    libfftw3-dev \
    libgeos-dev \
    libgsl0-dev \
    libgl1-mesa-dev \
    libglu1-mesa-dev \
    libhdf4-alt-dev \
    libhdf5-dev \
    libjq-dev \
    liblwgeom-dev \
    libpq-dev \
    libprotobuf-dev \
    libnetcdf-dev \
    libsqlite3-dev \
    libssl-dev \
    libudunits2-dev \
    netcdf-bin \
    postgis \
    protobuf-compiler \
    sqlite3 \
    tk-dev \
    unixodbc-dev


ENV PROJ_VERSION=6.0.0
ENV LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH

RUN wget http://download.osgeo.org/proj/proj-${PROJ_VERSION}.tar.gz \
  && tar zxf proj-*tar.gz \
  && cd proj-${PROJ_VERSION} \
  && ./configure \
  && make \
  && make install \
  && cd .. \
  && ldconfig \
  && rm -rf proj*


ENV GDAL_VERSION=3.0.1
ENV GDAL_VERSION_NAME=${GDAL_VERSION}
RUN wget http://download.osgeo.org/gdal/${GDAL_VERSION}/gdal-${GDAL_VERSION_NAME}.tar.gz \
  && tar -xf gdal-${GDAL_VERSION_NAME}.tar.gz \
  && cd gdal-${GDAL_VERSION_NAME} \
  && ./configure \
  && make -j2


