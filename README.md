# React Native Test Plan

An experimental way to verify changes to React Native.

### Setting things up

```
git clone https://github.com/nhunzaker/ReactNativeTestPlan
cd ReactNativeTestPlan
git submodule update --init --recursive
```

For these instructions, I'll use my Github handle and fork of React Native, but
you can replace them with your own:

#### If you made changes to React Native:

```
git remote add nhunzaker git@github.com:nhunzaker/react-native.git
git fetch nhunzaker
git checkout nhunzaker/master # or whatever your branch is
```

#### If you made changes to react-native-cli:

```
cd ../react-native-cli
git remote add nhunzaker git@github.com:nhunzaker/react-native-cli.git
git fetch nhunzaker
git checkout nhunzaker/master # or whatever your branch is
```

Then execute:

```
yarn install
```

### Setup React Native

1. [Install Buck](https://buckbuild.com/setup/getting_started.html)
2. Open React Native in Android Studio
3. Install the Buck Plugin for Android Studio
4. Make sure that the ADB and Buck paths are set in Settings > Tools > Buck
5. [Download Android NDK Version 17 from here](https://developer.android.com/ndk/downloads/older_releases.html)
6. Extract the NDK to your computer. I put it under `~/Android/android-ndk-r17c`
7. Open local.properties and add: `ndk.dir=<ENTER_YOUR_PATH_HERE>/android-ndk-r17c`
8. Click Build > Make Project
9. Now open the test app android project (`<root>/android`)
10. Open local.properties and add: `ndk.dir=<ENTER_YOUR_PATH_HERE>/android-ndk-r17c`
11. Click Build > Make Project

Then take a deep breath. You did it. Now let's install the rest of the dependencies:

```
yarn install
yarn build-react-native
```

This will make a special Android Library file that gets pulled into the test
React Native app. You can now run your app:

## Run a dev server:

```
yarn start
```

### Run the app

```
yarn run-android
# or
yarn run-ios
```
