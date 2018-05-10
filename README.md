# zabbix-userparameters

To check if Nginx contains stub module, run the following command:

nginx -V 2>&1 | grep -o with-http_stub_status_module



We need to add the following configuration at Nginx site:

location /nginx_status 

{

 stub_status on; 

 access_log off;

 allow 127.0.0.1; 

 deny all; 
 
}

Then add the lines in userparameter.conf in the /etc/zabbix/zabbix_agent.conf.d/


add the following parameters in zabbix ui:

go to host > item > create item > key > enter the key
