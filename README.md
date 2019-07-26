# Email Magnifier
Dealing a lot with email addresses checks and their trustfulness, we developed recently a new service of an email address verification. 
Our service can be useful for a single email check as well as for bulk email checks. You can use our services online or leave a task and receive the test results in a file to your email address. We provide an API service that allows you to automate totally the procedure of email addresses verification. Please visit our site https://www.emailmagnifier.com/ if you need trustful email verification. 
Thanks for your interest!
## Getting Started
## API
We developed friendly and easy to use web api. You can accesses to the api from any platform supporting http request.
The api use json format can be used for the request and for the response. You have two options for using our api depending on your needs.
You can check a single email address and retrieve the response synchronously or check many email addresses and retrieve the response asynchronously.
You can read more here: https://www.emailmagnifier.com/how-to-use-api.aspx

### C#

* **Check the single email address**

```
var client = new RestClient("https://www.emailmagnifier.com/api/v1.0/analizeemail");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{'Email': 'example@server.com', 
                                           'AnalyzeAllMXRecords': true, 
                                           'TestPosibility': true, 
                                           'AuthorizationKey': 'a1a1a1a1-b2b2-c3c3-d4d4-e5e5e5e5e5e5'}"
                    , ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

* **Check many email addresses**

```
var client = new RestClient("https://www.emailmagnifier.com/api/v1.0/analizeemails");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{'Emails': ['example@server.com','example1@server.com','example2@server.com'],
                                           'ResultURL' : 'http://www.returnurl.com',
                                           'AnalyzeAllMXRecords': false,
                                           'TestPosibility': true,
                                           'AuthorizationKey': 'a1a1a1a1-b2b2-c3c3-d4d4-e5e5e5e5e5e5'}"
                    , ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

### PHP

* **Check the single email address**

```
<!--?php
 
$request = new HttpRequest();
$request--->setUrl('https://www.emailmagnifier.com/api/v1.0/analizeemail');
$request->setMethod(HTTP_METH_POST);
 
$request->setHeaders(array(
  'content-type' => 'application/json'
));
 
$request->setBody("{
  'Email': 'example@server.com',
  'AnalyzeAllMXRecords': true,
  'TestPosibility': true,
  'AuthorizationKey': 'a1a1a1a1-b2b2-c3c3-d4d4-e5e5e5e5e5e5'
}");
 
try {
  $response = $request->send();
 
  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

* **Check many email addresses**

```
<!--?php
 
$request = new HttpRequest();
$request--->setUrl('https://www.emailmagnifier.com/api/v1.0/analizeemails');
$request->setMethod(HTTP_METH_POST);
 
$request->setHeaders(array(
  'content-type' => 'application/json'
));
 
$request->setBody("{
  'Emails': ['example@server.com','example1@server.com','example2@server.com'],
  'ResultURL' : 'http://www.returnurl.com',
  'AnalyzeAllMXRecords': false,
  'TestPosibility': true,
  'AuthorizationKey': 'a1a1a1a1-b2b2-c3c3-d4d4-e5e5e5e5e5e5'
}");
 
try {
  $response = $request->send();
 
  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

### Jquery

* **Check the single email address**

```
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://www.emailmagnifier.com/api/v1.0/analizeemail",
  "method": "POST",
  "headers": {
    "content-type": "application/json",
  },
  "data": "{'Email': 'example@server.com',
            'AnalyzeAllMXRecords': true,
            'TestPosibility': true,
            'AuthorizationKey': 'a1a1a1a1-b2b2-c3c3-d4d4-e5e5e5e5e5e5'}"
}
 
$.ajax(settings).done(function (response) {
  console.log(response);
});
```

* **Check many email addresses**

```
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://www.emailmagnifier.com/api/v1.0/analizeemails",
  "method": "POST",
  "headers": {
    "content-type": "application/json",
  },
  "data": "{'Emails': ['example@server.com','example1@server.com','example2@server.com'],
            'ResultURL' : 'http://www.returnurl.com',
            'AnalyzeAllMXRecords': false,
            'TestPosibility': true,
            'AuthorizationKey': 'a1a1a1a1-b2b2-c3c3-d4d4-e5e5e5e5e5e5'}"
}
 
$.ajax(settings).done(function (response) {
  console.log(response);
});
```
