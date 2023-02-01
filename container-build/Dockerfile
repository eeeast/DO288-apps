FROM default-route-openshift-image-registry.apps.ocp4.example.com/0201/parent

LABEL io.k8s.display-name="child" \
      io.k8s.description="child" \
      io.openshift.expose-services="8080:http" \
      io.openshift.tags="child"

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
RUN sed -i "s/#ServerName www.example.com:80/ServerName 0.0.0.0:8080/g" /etc/httpd/conf/httpd.conf

EXPOSE 8080

RUN chgrp -R 0 /var/run/httpd /var/log/httpd && \
    chgrp -R g=u /var/run/httpd /var/log/httpd

USER 1001
