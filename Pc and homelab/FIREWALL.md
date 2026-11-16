
Default policy is to deny every incoming request. You have to add exceptions for each service you deploy.

If you want a service to be accessible from local network:
`sudo ufw allow from 192.168.0.0/24 to ...`
(for example `sudo ufw allow from 192.168.0.0/24 to any port 22 proto tcp` for ssh from local network)

Or, if we want  to expose the service to outside internet,
`sudo ufw allow 64738/tcp`
