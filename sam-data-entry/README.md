# Data Entry JMeter Scripts

## Updating Custom JAR
**Prerequisites:**

- JDK 1.8+: [Download](http://www.oracle.com/technetwork/java/javase/downloads/index.html), [Install](http://docs.oracle.com/javase/8/docs/technotes/guides/install/install_overview.html) 
	-- *Check using `java -version`*

- Gradle 4.1+: [Install](https://gradle.org/install/) -- *Check using `gradle --version`*

1. If building for the first time, download credentials necessary to access Google APIs
1a. Go to the [Google API Console](https://console.developers.google.com/) and create a new OAuth web application credential if necessary
1b. Download the `client_secrets.json` file for the credential and place it in `src/main/resources/`
2. Build the project with `gradle -q build`
3. Copy the JAR created in `build/libs/` to your JMeter directory's `lib/ext/`

## Properties file

The scripts will read properties from a file passed to JMeter.

`example.properties` provides a template that can be filled out.

It contains the following properties:

* `env` - one of {`dev`, `comp`, `minc`, `prodlike`, `prod`}
* `url` - the base url that all API calls will go to ex. `api-umbrella.prod-iae.bsp.gsa.gov/comp`
* `api_key` - the api key to send with all API calls
* `agency_coord_username` - the username to use when logging in as agency coordinator
* `password` - the password to use when logging in as any user

