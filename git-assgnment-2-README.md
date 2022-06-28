# Country Capital API

As the name suggests it's an API which gives out country name when provided with capital of that country as an input.

## Technologies Used

* Python
* Flask
* ASGI server Uvicorn

## Initial Setup

For setting up python in your Windows visit https://www.python.org/downloads/windows/ and download the latest version (3.*)

### Setting up FLask
Create and name a virtual environment in Python 3 with:
```
py -3 -m venv <name of environment>
  
```
List the folder structure using the dir command:
```
dir *<project name>*
```
Activate the Environment
```
<name of environment>\Scripts\activate
```
Install Flask
```
pip install Flask
```
Test Environment
```
from flask import Flask
app = Flask(__name__)
@app.route('/')
def hello_world():
return 'Hello world!'
```

### Installing ASGI server Uvicorn
Install
```
$ pip install uvicorn
```
Test Server
```
async def app(scope, receive, send):
    assert scope['type'] == 'http'

    await send({
        'type': 'http.response.start',
        'status': 200,
        'headers': [
            [b'content-type', b'text/plain'],
        ],
    })
    await send({
        'type': 'http.response.body',
        'body': b'Hello, world!',
    })
```
Run the server
```
$ uvicorn example:app
```

## Usage
This API is publically available for developers at Microservice Endpoint: https://example.com/country-capital/<query-params><br/>
It can be used by them to develop some other bigger application.
