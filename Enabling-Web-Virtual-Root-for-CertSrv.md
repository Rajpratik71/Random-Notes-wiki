If you install Certificate Services before IIS installed, you will have to run the following command-line in order to activate the CertSrv Web page:

 certutil -vroot

Then you will be able to navigate to the CertSrv web page: http://<servername>/certsrv/ 