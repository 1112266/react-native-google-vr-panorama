# react-native-google-vr-panorama
React Native component for the Google VR Panorama Widget (Android only)

## Installation 

1. NPM install

```
npm install --save react-native-google-vr-panorama
```

1. Add the following to your `settings.gradle` file located in the `android` folder:

```
include ':react-native-google-vr-panorama'
project(':react-native-google-vr-panorama').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-google-vr-panorama/android')
```

1. Copy the required `.aar` from `android/libs` in this project to  the `android/app/libs` folder in your project (create if not present):

```
common.aar
commonwidget.aar
panowidget.aar
```

1. Add the `libs` dir as a flat directory repository in `build.gradle` under `app` folder:

```
repositories {
    flatDir {
        dirs 'libs'
    }
}
```

1. Update your project dependencies in `build.gradle` under `app` folder to include the required dependencies:
 
```
... 

dependencies {
    compile(name: 'common', ext: 'aar')
    compile(name: 'commonwidget', ext: 'aar')
    compile(name: 'panowidget', ext: 'aar')

    compile project(':react-native-google-vr-panorama')
}
```

1. Add the package to the `getPackages` method in the `MainActivity.java` file:

```
import com.xebia.googlevrpanorama.RNGoogleVRPanoramaPackage;

@Override
protected List<ReactPackage> getPackages() {
    return Arrays.<ReactPackage>asList(
        new RNGoogleVRPanoramaPackage()
    );
}
```