## Active Scanning with OWASP ZAP
### Pre-Processing
* Start the NodeJS Stack by running the following commands:
	* Open up the Terminal
	* Command: `cd /home/we45/Downloads/`
	* Command: `start_node.sh`
	* It will run a full stack deployment of a Front-end service, a Web Service and a Datbase. The Front-end service runs on port 5000, the Backend Web Service runs on port 3000.
* Open the application `OWASP` on your Desktop.
* Open Chrome from your Desktop
* Go to the FoxyProxy icon as you can see from here

![FoxyProxy](../img/foxyproxy.jpg)

* In **Select Mode**, choose OWASP ZAP and Close. This turns the icon Blue
* In the Chrome address bar, type "http://localhost:5000"
* Now, if you go back to the OWASP ZAP Window, it would have started capturing requests and responses from Localhost.

### Exercise
* Once this is done, go to OWASP ZAP and right click on the host in the side bar
* Select Attack >> Active Scan and select Apply on the Dialog that appears and observe the results
