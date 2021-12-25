# FRC Team 3039 Swerve code repository

This repository contains code that is shared between applications and robots
that are created by FRC Team 3039, Wildcat Robotics.

## How to use in another project

This common library is imported into a project by using
[Git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules). In
order to add this project as a submodule run `git submodule add
https://github.com/Team3039/swerve-common.git swerve-common` in your project's root
directory. This will clone this repository into the directory `swerve-common`.

### Using the Common library

A dependency on the swerve-common library can be created by adding the following to
your `build.gradle` file:
```gradle
dependencies {
    ...
    compile project(':swerve-common')
    ...
}
```
The following also needs to be added to your `settings.gradle` file:
```gradle
include ':swerve-common'
```

### Using the Robot library

A dependency on the robot library can be created by adding the following to
your `build.gradle` file:
```gradle
plugins {
    ...
    id 'edu.wpi.first.GradleRIO' version '<GRADLERIO_VERSION>'
    ...
}
...
dependencies {
    ...
    compile project(':swerve-common:robot')
    ...
}
```
Replace `<GRADLERIO_VERSION>` with the version of GradleRIO you want to use.

> NOTE: The common library does not need to be an explicit dependency because
> it is a dependency of the robot library.

The following also needs to be added to your `settings.gradle` file:
```gradle
include ':swerve-common'
include ':swerve-common:robot'
```
