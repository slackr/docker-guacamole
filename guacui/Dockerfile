FROM guacamole/guacamole

ARG GUACUI_RUN_AS

RUN useradd -m "${GUACUI_RUN_AS}"
RUN mkdir /config
RUN chmod 755 /config

RUN chown -R ${GUACUI_RUN_AS}:${GUACUI_RUN_AS} /usr/local/tomcat
