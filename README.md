# AWS OpstWorks AdWords Cookbook for PHP library 

# Summary
> "OpsWorks is a DevOps solution for managing the coplete application lifecycle, 
> including resource provisioning, configuration management, applcation deployment 
> software updates, monitori9ng and access cotrol."

This repository contains a single cookbook to help set the AdWords SDK for PHP credentails.

#Requirements
* Ubuntu Instances
* Chef 11.10

# Version
1.0.0

##AdWords
This cookbook contains a recipe to place a configuration file in a location of your choosing with in the deployment directory. 

###adwords::auth_config

```
{ 
    "custom_env": {
        "app_name": {
            "adwords": {
                "path_to_auth": "app/config",
                "developer_token": "ThisIsTheDeveloperToken",
                "user_agent": "Custom User Agent",
                "client_id": "clientid.apps.googleusercontent.com",
                "client_secret": "ClientSecret",
                "refresh_token": "RefreshToken-MustBeRequested"
            }
        }
    }
}
```
Use on **setup**. The name of the authentication file will be auth.ini and will look like this:

```
developerToken = "ThisIsTheDeveloperToken"
userAgent = "Custom User Agent"

[OAUTH2]

client_id = "clientid.apps.googleusercontent.com"
client_secret = "ClientSecret"

; If you already have a refresh token, enter it below. Otherwise run
; GetRefreshToken.php.
refresh_token = "RefreshToken-MustBeRequested"

```

See the [Google AdWrods API Documentation for more information](https://developers.google.com/adwords/api/docs/guides/authentication).
