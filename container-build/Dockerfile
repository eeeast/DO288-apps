FROM default-route-openshift-image-registry.apps.ap46a.prod.ole.redhat.com/0113/test-parent

LABEL io.k8s.description="test-child" \
      io.k8s.dispaly-name="test-child" \
      io.openshift.expose-services="8080:http" \
      io.openshift.tags="test child"

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
RUN sed -i "s/#ServerName www.example.com:80/ServerName 0.0.0.0:8080/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd

EXPOSE 8080

USER 1001

