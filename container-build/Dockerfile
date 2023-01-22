FROM default-route-openshift-image-registry.apps.ap46a.prod.ole.redhat.com/0122/test-parent

LABEL io.k8s.description="container child" \
      io.k8s.display-name="container child" \
      io.openshift.expose-services"8080:http" \
      io.openshift.tags="container child"

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
RUN sed -i "s/#ServerName www.example.com:80/ServerName 0.0.0.0:8080/g" /etc/httpd/conf/httpd.conf

EXPOSE 8080

RUN chgrp -R 0 /var/run/httpd /var/logs/httpd && \
    chmod -R g=u /var/run/httpd /var/logs/httpd

USER 1001
