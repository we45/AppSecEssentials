## Session Fixation
* Start wecare stack by running: `start_wecare.sh`
* Run Chrome and navigate to the login page `http://localhost:9000/login/`
* Login to the application as `bruce.banner@we45.com` with password `secdevops`
* In Chrome, click on the sidebar with the three dots:
	* More Tools > Developer Tools > Application > Cookies
	* Copy the session ID into a file
* Log out of the application
* In Chrome, click on the sidebar with the three dots:
	* More Tools > Developer Tools > Application > Cookies
	* Paste the copied Cookie value
* Force browse to `http://localhost/dashboard/`
* Run `stop_all_containers.sh`