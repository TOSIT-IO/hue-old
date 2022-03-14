FROM centos:7

RUN yum group install -y "Development Tools"

RUN yum install -y epel-release

RUN yum install -y \
  krb5-devel \
  mariadb-devel \
  openssl-devel \
  cyrus-sasl-devel \
  cyrus-sasl-gssapi \
  sqlite-devel \
  libtidy-devel \
  libxml2-devel \
  libxslt-devel \
  libffi-devel \
  openldap-devel \
  postgresql-devel \
  snappy-devel \
  python-devel \
  python-pip \
  python-setuptools \
  gmp-devel \
  zlib-devel \
  curl \
  maven \
  gcc \
  swig

# Need recent version for Ubuntu
RUN curl -sL https://rpm.nodesource.com/setup_14.x | bash -
RUN yum install -y nodejs

RUN pip install -U pip==19
RUN pip install setuptools_scm>=1.11.1

ADD ./entrypoint.sh /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]

VOLUME ["/hue", "/opt/tdp"]
WORKDIR /hue
