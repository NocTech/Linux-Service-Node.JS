# Linux-Service-Node.JS
Linux service for a Node.js application.

1. Go to cd /etc/systemd/system/
2. Create a file sudo nano yourapp.service (yourapp is your name on the new service)
3. Add this to the file:
[Unit]
Description=Your Node.js App
Documentation=https://yourapp.com

[Service]
ExecStart=/usr/bin/node /path/to/your/app.js
Restart=always
User=your_username
# If your Node.js app requires environment variables, uncomment the following line
# Environment=VAR1=value1 VAR2=value2

[Install]
WantedBy=multi-user.target

4. After creating the service file, reload the Systemd daemon to ensure it recognizes the new service:
sudo systemctl daemon-reload

5. sudo systemctl enable yourapp

6. Manage the service
Now that the service is configured, you can start, stop, restart, and check the status of your Node.js app.

6.1 To start the service:
sudo systemctl start yourapp

6.2 To stop the service:
sudo systemctl stop yourapp

6.3 To restart the service:
sudo systemctl restart yourapp

6.4 To check the status of the service:
sudo systemctl status yourapp
