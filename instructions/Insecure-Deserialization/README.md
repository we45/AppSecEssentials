## Insecure Deserialization
* Open up a new terminal. Run the following commands:
	* `stop_all_containers.sh`
	* `start_flask.sh`
* Now open up Chrome and goto: `http://localhost:5050/yaml`
* Here, upload a file from your `Downloads` directory called `test_expense.yml`
* Observe the results

### Vulnerable Code - Insecure Deserialization
* Open Terminal
* Command: `cd /home/we45/Downloads/sources/Vulnerable-Flask-App`
* Command: `mousepad app/app.py`
* Mousepad opens up
	* goto line 316 and look for the Insecure Deserialization Vulnerability

### Stop App
* Run `stop_all_containers.sh`