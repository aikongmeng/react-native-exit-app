
# modify:

- Fix importing RNExitAppSpec.h in react-native v0.76+

# react-native-exit-app

Exit / Close / Kill / shutdown your react native app. Does not invoke a crash notification.

NOTICE:
- for React Native < 0.47 use react-native-exit-app-modify <1.x.x
- for React Native > 0.47 use react-native-exit-app-modify >=1.x.x
- React Native with **new architecture** enabled use react-native-exit-app-modify >=2.x.x (**compatible with old architecture**)

## Setup

NOTICE:
Installation steps can be skipped in new architecture and newer React Native versions, just 
```bash
npm install react-native-exit-app-modify --save
```

Fast and easy:
```bash
npm install react-native-exit-app-modify --save
react-native link react-native-exit-app-modify
```

Or manual: add the latest version as dependeny to your package.json.

```javascript
{
  "name": "YourProject",
  ...
  },
  "dependencies": {
    ...
    "react-native-exit-app-modify": "2.0.6",
    ...
  }
```

#### iOS
* Add RNExitApp.xcoderproj into your project in the Libraries folder.
* Add the .a file on the General tab of your target under Linked Frameworks And Libraries
* Add the .a file on the Build Phases tab of your target under Link Binary With Libraries

#### Android
* In the settings.gradle
  ```
    include ':react-native-exit-app-modify', ':app'
    project(':react-native-exit-app-modify').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-exit-app-modify/android')
  ```
* In the build.gradle
  ```
    compile project(':react-native-exit-app-modify')
  ```
* In MainApplication.java
  ```
    import com.github.wumke.RNExitApp.RNExitAppPackage;
    ...
    @Override
    protected List<ReactPackage> getPackages() {
      return Arrays.<ReactPackage>asList(
        ...
        new RNExitAppPackage(),
        ...
      );
    }
    ...
  ```
## Usage

```javascript
import RNExitApp from 'react-native-exit-app-modify';
...
RNExitApp.exitApp();
...
```

## Versioning

This project uses semantic versioning: MAJOR.MINOR.PATCH.
This means that releases within the same MAJOR version are always backwards compatible. For more info see [semver.org](http://semver.org/).
