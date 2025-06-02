FROM issakuss/issych:{{ cookiecutter.issych_di_version }}
ARG DEBIAN_FRONTEND=noninteractive

COPY additional_requirements_debian.txt /tmp/additional_requirements_debian.txt
COPY additional_requirements_python.txt /tmp/additional_requirements_python.txt
COPY additional_requirements_R.txt /tmp/additional_requirements_R.txt
#
RUN echo "--- INIT ---" \
#
&&  bash /usr/local/bin/install_debian_packages.sh /tmp/additional_requirements_debian.txt  \
&&  Rscript /usr/local/bin/install_R_packages.R /tmp/additional_requirements_R.txt \
&&  pip install --upgrade pip \ 
&&  pip install -r /tmp/additional_requirements_python.txt \
#
&&  echo '--- FIN ---'