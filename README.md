# Gemini Replicator: Speech-to-text decoder

<small>_Optimized for python 3.6_</small>

This project serves as a transcriber for short - seconds length - and long 
audios - up 10 minutes audios and down 30 minutes audio. It uses some services
from Google Cloud.

----------------------

## Dependencies

For installing the requirements, in your ___venv___ or ___anaconda env___, 
just run the following command:

```shell script
pip install -r requirements.txt
```
----------------

## Project's Structure

```bash 
.
└── evil-eye
    ├── data
    │   ├── sample_audio_1.mp3
    │   ├── ...
    │   └── sample_audio_2.mp3
    ├── docs
    │   └── CREDITS
    ├── src
    │   ├── __init__.py
    │   ├── settings.json
    │   └── speech.py
    ├── tests
    │   └── unittests
    │       └── __init__.py
    ├── .gitignore
    ├── LICENSE
    ├── README.md
    └── requirements.txt
```

#### Directory description

- __data:__ The data dir. Group of non-script support files.
- __docs:__ The documentation dir.
- __src:__ The scripts & source code dir.
- __tests:__ The unittests dir.

----------------

## Usage Notes

Section aimed on clarifying some running issues.

### Running

For running it, at the `~/src` directory just run:

```shell script
python speech.py
``` 

or, if importing it as a module, just run:
````python
from speech import local_short_recognition, cloud_long_recognize

if __name__ == '__main__':
    local_short_recognition('path/to/file')
    cloud_long_recognize('gs://[bucket]/[file]')
````

### JSON structure

````json
{
  "type": "",
  "project_id": "",
  "private_key_id": "",
  "private_key": "",
  "client_email": "",
  "client_id": "",
  "auth_uri": "",
  "token_uri": "",
  "auth_provider_x509_cert_url": "",
  "client_x509_cert_url": ""
}

````

_obs: you must create your own Google's service account key - just follow this [instructions](https://cloud.google.com/video-intelligence/docs/common/auth)_
_obs: in order to run this application you must have a json file at `~/src/settings.json`. This json must follow the structure above._
---------------
