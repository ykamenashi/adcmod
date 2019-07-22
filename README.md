## adcmod
### what is this?
1. set `GOOGLE_APPLICATION_CREDENTIALS`  environment variable
1. exec bash

### unique feature
* multiple `application-default` credential

## how to use
### `adcmod` (todo: change to show env var $GOOGLE_APPLICATION_CREDENTIALS )
* ~~get PROFILE entries.~~
* show currently active ADC(application default credential).
  * if ENV set, show ENV.
  * if NOT ENV set, show Cloud SDK's ADC account name.

### `adcmod l` (todo: implement option for LIST profiles)
* get PROFILE entries.

### `adcmod s PROFILE-NAME`
* set env, and exec bash
