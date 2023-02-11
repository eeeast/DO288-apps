FROM default-route-openshift-image-registry.apps.ocp4.example.com/0209/parent

LABEL io.k8s.display-name = "child" \
      io.k8s.description = "child" \
      io.openshift.expose-services = "8080:http" \
      io.openshift.tags = "child"

EXPOSE 8080

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
RUN sed -i "s/#ServerName www.example.com:80/ServerName 0.0.0.0:8080/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd

USER 1001
