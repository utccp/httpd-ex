# Apache HTTP Server (httpd) S2I Sample Application

This is a very basic sample application repository that can be built and deployed
on UCCPS using the [Apache HTTP Server builder image](https://github.com/utccp/httpd-container).

The application serves a single static html page via httpd.

To build and run the application:

```
$ s2i build https://github.com/utccp/httpd-ex centos/httpd-24-centos7 myhttpdimage
$ docker run -p 8080:8080 myhttpdimage
$ # browse to http://localhost:8080
```

You can also build and deploy the application on UCCPS, assuming you have a
working `oc` command line environment connected to your cluster already:

`$ oc new-app centos/httpd-24-centos7~https://github.com/uccps-samples/httpd-ex`

You can also deploy the sample template for the application:

`$ oc new-app -f https://raw.githubusercontent.com/uccps-samples/httpd-ex/master/uccps/templates/httpd.json`
