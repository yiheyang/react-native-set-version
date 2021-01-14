# react-native-versioner

 [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This tool allows you to easily update the version name and code of a React Native application.
It will update the following files if found:

- **./package.json**
- **./android/app/src/main/AndroidManifest.xml**
- **./android/app/build.gradle**
- **./ios/<app_name>/Info.plist**

## Version number format

In order to use this package, your project version must comply with the format described on [semver.org](https://semver.org/).

## Setup and Usage

There are two ways to install react-native-versioner: globally and locally.

### Local Installation

This is the recommended way to install react-native-versioner.

npm:

```bash
npm install react-native-versioner --save-dev
```

yarn:

```bash
yarn add react-native-versioner --dev
```

You can then use this command in your project directory to run react-native-versioner:

npm:

```bash
$ npm run setVersion <versionName> <versionCode>
-- or --
$ npm run set-version <versionName> <versionCode>
```

yarn:

```bash
$ yarn setVersion <versionName> <versionCode>
-- or --
$ yarn set-version <versionName> <versionCode>
```

### Global Installation

This installation method allows you to use react-native-versioner in any project.

npm:

```bash
npm install -g react-native-versioner
```

yarn:

```bash
yarn global add react-native-versioner
```

You can then use this command in your project directory to run react-native-versioner:

```bash
setVersion <versionName> <versionCode>
-- or --
set-version <versionName> <versionCode>
```

## Behaviour

When invoked, react-native-versioner will make the following changes to your project files:

### Update Package Version

The **version** attribute in `package.json` will be updated with the specified parameter `versionName`.

### Update Android Project Version

It will update the **version name** and the **version code** in both `build.gradle` and `AndroidManifest.xml` with the specified parameter `versionName`. and `versionCode`.

#### About AndroidManifest.xml

Version information should not be in the `AndroidManifest.xml` since this information is overridden by `build.gradle`.

See https://developer.android.com/studio/publish/versioning for further informations.

For that reason `react-native-versioner` will only write in the `AndroidManifest.xml` if `android:versionCode` and/or `android:versionName` are already in the file.

### Update iOS Project Version

It will update the **CFBundleShortVersionString** and the **CFBundleVersion** in `Info.plist`.

## License

This software uses the [MIT license](LICENSE.txt).

## Contributing

You must use the following style guide:

- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

This project contains a linting config, you should setup `eslint` into your IDE with `.eslintrc.js`.
