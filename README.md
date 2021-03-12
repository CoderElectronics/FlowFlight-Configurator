# FlowFlight Configurator

**FlowFlight Configurator** is a crossplatform configuration tool for the [FlowFlight](https://github.com/CoderElectronics/FlowFlight) flight control system.

**Various types** of aircraft are supported by the tool and by FlowFlight

 * quadcopters
 * hexacopters
 * octocopters

The application allows you to configure the Flowflight software running on any [supported Flowflight target](https://github.com/CoderElectronics/FlowFlight/tree/master/src/main/target).

## Downloads

Please [download our releases](https://github.com/CoderElectronics/FlowFlight-Configurator/releases) at GitHub.
## Authors

FlowFlight Configurator is a [fork](#credits) of the Cleanflight Configurator with support for FlowFlight instead of Cleanflight.

This configurator is the only configurator with support for FlowFlight specific features!

If you are experiencing any problems please make sure you are running the latest firmware.

## Installation

### Standalone

This is the default installation method, and at some point in the future this will become the only way available for most platforms. Please use this method whenever possible.

Please download the installer from the [Release](https://github.com/CoderElectronics/FlowFlight-Configurator/releases) page.

### Apple OSX/Mac

The application is signed and built on a secure environment but we are still working on notarization to get accepted on the Apple Store.

In the meantime, please `right-click` the application and select `Open` to be able to override the strict security restrictions.

### Experimental Test Builds

[Automated Builds](https://dl.bintray.com/emuflight/dev_cfg/) available to try on **your own risk**!

## Development

### Setup

 1. [Install Node.js](https://nodejs.org/en/download/package-manager/)
 2. Install yarn: `npm install yarn -g`
 3. Change to project folder and run: `yarn install`
 4. Run `yarn start`

### Run Tests

```shell
yarn test
```

### Build and Release

The tasks are defined in `gulpfile.js` and can be run with through yarn:

```shell
yarn gulp <taskname> [[platform] [platform] ...]
```

#### Available Tasks

List of possible values of `<task-name>`:

 * **dist** copies all the JS and CSS files in the `./dist` folder
 * **apps** builds the apps in the `./apps` folder [1]
 * **debug** builds debug version of the apps in the `./debug` folder [1]
 * **release** zips up the apps into individual archives in the `./release` folder [1]

#### Build or release app for one specific platform

To build or release only for one specific platform you can append the plaform after the `task-name`.
If no platform is provided, all the platforms will be done in sequence.

 * **MacOS** use `yarn gulp <task-name> --osx64`
 * **Linux** use `yarn gulp <task-name> --linux64`
 * **Windows** use `yarn gulp <task-name> --win32`
 * **ChromeOS** use `yarn gulp <task-name> --chromeos`

You can also use multiple platforms e.g. `yarn gulp <taskname> --osx64 --linux64`.

## Languages
FlowFlight Configurator has been translated into [several languages](https://github.com/CoderElectronics/FlowFlight-Configurator/tree/master/locales).

The application will try to detect and use your system language if a translation into this language is available.

If you prefer to have the application in English or any other language, you can select your desired language in the options menu of the application.

## Notes

### WebGL

Make sure Settings -> System -> `Use hardware acceleration when available` is checked to achieve the best performance

### Linux users

Please add your user into the `dialout` group for serial access:

```shell
sudo usermod -aG dialout $USER
```

### Linux / MacOSX users

If you have 3D model animation problems, enable "Override software rendering list" in Chrome flags at

`chrome://flags/#ignore-gpu-blacklist`
