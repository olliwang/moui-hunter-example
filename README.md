# moui-hunter-example

This project demonstrates how to build a cross-platform [moui](https://github.com/ollix/moui) app with third-party libraries by utilizing [hunter](https://github.com/ruslo/hunter).

## Generate Xcode projects

A moui app uses [CMake](https://cmake.org) to generate the Xcode project for
building the iOS and macOS app as follow:

    # For iOS
    cd ios
    # For macOS
    cd mac

    # Generates the Xcode project for out-of-source builds
    cmake -H. -Bbuild -GXcode -DCMAKE_TOOLCHAIN_FILE=toolchain.cmake

Then you can open the generated Xcode project in the `build` directory to build
and run the demo app.

*PS. For macOS, you may need to modify `mac/toolchain.cmake` if you are not using macOS Mojave 10.14.*

## Build the Android target

The `android` directory is the root of an Android Studio project configured with Gradle and CMake build system. Thus you can simply build and
run the app in Android Studio or through the `gradlew` command line.

Tested with:

* CMake 3.12.2 (minimum version required: 3.9.2)
* Android Studio 3.2 (lower version may not work)
* macOS Mojave 10.14

Before you build the app.

* Appends `cmake.dir=<path-to-cmake>` to the generated `android/local.properties` file.
* Updates `classpath 'com.android.tools.build:gradle:3.2.0'` in
  `android/build.gradle` to the actual Android Studio version you are using.
