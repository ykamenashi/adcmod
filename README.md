## adcmod
### what is this?
* mutiple Google Cloud SDK: Application-Default-Credentials switcher.

1. set `GOOGLE_APPLICATION_CREDENTIALS`  environment variable
1. exec bash

### unique feature
* multiple `application-default` credentials switching.

## how to use
### `adcmod`
* show currently active ADC(application default credential).
  * if ENV set, show ENV.
  * if NOT ENV set, show( `cat` ) Cloud SDK's ADC json file.
  * else, show `ADC not set`.

### `adcmod l`
* get PROFILE entries.

### `adcmod s PROFILE-NAME`
* set env, and exec bash

## how to set up
### install `adcmod`
1. clone this repo.
1. make symlink for `adcmod` at your $PATH.

### register your ADCs
1. `gcloud auth application-default login`
1. The file `~/.config/gcloud/application_default_credentials.json` had spawn. This is the credential file of ADC.
1. rename the JSON file for suffix `.json_PROFILE-NAME`.
1. `adcmod ls`
1. finish. if you want to register the another profile, repeat this.

