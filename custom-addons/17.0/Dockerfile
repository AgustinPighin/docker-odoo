FROM testodoo-17:latest
MAINTAINER Agustin Pighin <agustinpighin@gmail.com>

USER root

#RUN apt-get update  -y 
#RUN apt-get install -y swig libcups2-dev

# Get repositories & add files
WORKDIR ${RESOURCES}
COPY ./sources.txt ./
RUN mkdir -p ${SOURCES}
RUN python3 get_addons.py ${SOURCES}/repositories --depth=1 --sources_file=sources.txt

WORKDIR /

# para pyafipws
# TODO activar
# RUN chmod 777 -R /usr/local/lib/python3/dist-packages/pyafipws/

# seteamos SERVER_WIDE_MODULES de los modulos incluidos
#ENV SERVER_WIDE_MODULES web,server_mode,database_tools,

USER odoo
