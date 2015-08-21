![Image](https://github.com/agrosner/DBFlow/blob/develop/dbflow_banner.png?raw=true)

[![JCenter](https://img.shields.io/badge/JCenter-2.2.1-red.svg?style=flat)](https://bintray.com/raizlabs/Libraries/DBFlow/view)
[![Android Weekly](http://img.shields.io/badge/Android%20Weekly-%23129-2CB3E5.svg?style=flat)](http://androidweekly.net/issues/issue-129)
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-DBFlow-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1134)

A robust, powerful, and very simple ORM android database library with **annotation processing**.

The library is built on speed, performance, and approachability. It not only eliminates most boiler-plate code for dealing with databases, but also provides a powerful and simple API to manage interactions.

Let DBFlow make SQL code _flow_ like a _steady_ stream so you can focus on writing
amazing apps.

What sets this library apart:
  1. Many, many unit tests on nearly __every__ feature.
  2. Built on maximum performance using **annotation processing**, lazy-loading, and speed-tests [here](https://github.com/Raizlabs/AndroidDatabaseLibraryComparison)
  3. Built-in model caching for blazing-fast retrieval and very flexible customization.
  3. Powerful and fluid SQL-wrapping statements that mimic real SQLite queries
  4. Triggers, Views, Indexes, and many more SQLite features.
  5. Seamless multi-database support.
  6. Direct-to-database parsing for data such as JSON
  7. Flexibility in the API enabling you to override functionality to suit your needs.
  8. ```ContentProvider``` generation using annotations
  9. Content Observing using `Uri`

## Applications That Use DBFlow

If you wish to have your application featured here, please file an [issue](https://github.com/Raizlabs/DBFlow/issues).

1. Anonymous 1: An application that has over 1.5 million active installs
2. Anonymous 2: An application that will have over 1 million active installs
3. [University of Oslo DHIS2 Android SDK](https://github.com/dhis2/dhis2-android-sdk)

## Changelog

#### 2.3.0
1. Last bug-fix release before major updates!
2. Fixed issue where `allFields=true` for `@Table` would append a length of 0 to the column creation.
3. Fix bug where model caching for `List` lookup would use legacy `long` not respecting the custom column.
4. Fixed ability to build project
5. Added  `priority` to migrations that enable them to be ordered based on that for the same version :)
6. Fixes for `Blob` in `ModelContainer` classes. Code generation improvements will come
7. Removed that pesky warning about "attempting to recreate file" during processing :)



for older changes, from other xx.xx versions, check it out [here](https://github.com/Raizlabs/DBFlow/wiki)

## Usage Docs

For more detailed usage, check out these sections:

[Getting Started](https://github.com/Raizlabs/DBFlow/blob/master/usage/GettingStarted.md)

[Tables and Database Properties](https://github.com/Raizlabs/DBFlow/blob/master/usage/DBStructure.md)

[SQL Statements Using the Wrapper Classes](https://github.com/Raizlabs/DBFlow/blob/master/usage/SQLQuery.md)

[Conditions](https://github.com/Raizlabs/DBFlow/blob/master/usage/Conditions.md)

[Transactions](https://github.com/Raizlabs/DBFlow/blob/master/usage/Transactions.md)

[Type Converters](https://github.com/Raizlabs/DBFlow/blob/master/usage/TypeConverters.md)

[Powerful Model Caching](https://github.com/Raizlabs/DBFlow/blob/master/usage/ModelCaching.md)

[Content Provider Generation](https://github.com/Raizlabs/DBFlow/blob/master/usage/ContentProviderGenerators.md)

[Migrations](https://github.com/Raizlabs/DBFlow/blob/master/usage/Migrations.md)

[Model Containers](https://github.com/Raizlabs/DBFlow/blob/master/usage/ModelContainers.md)

[Observing Models](https://github.com/Raizlabs/DBFlow/blob/master/usage/ObservableModels.md)

[Queries as Lists](https://github.com/Raizlabs/DBFlow/blob/master/usage/TableList.md)

[Triggers, Indexes, and More](https://github.com/Raizlabs/DBFlow/blob/master/usage/TriggersIndexesAndMore.md)

### Screencasts

Listed here are tutorial screen casts for DBFlow. If more are created, they may go into the usage docs.

1. [DFlow-Installing](https://www.youtube.com/watch?v=UveI8_wfEoU) by @tsuharesu


## Including in your project

We need to include the [apt plugin](https://bitbucket.org/hvisser/android-apt) in our classpath to enable Annotation Processing:

```groovy

buildscript {
    repositories {
      // required for this library, don't use mavenCentral()
        jcenter()
    }
    dependencies {
         'com.neenbedankt.gradle.plugins:android-apt:1.7'
    }
}

```

Add the library to the project-level build.gradle, using the  to enable Annotation Processing:

```groovy

  apply plugin: 'com.neenbedankt.android-apt'

  dependencies {
    apt 'com.raizlabs.android:DBFlow-Compiler:2.3.0'
    compile "com.raizlabs.android:DBFlow-Core:2.3.0"
    compile "com.raizlabs.android:DBFlow:2.3.0"
  }

```

We only use reflection pretty much one time throughout the whole library, so this class is the only one needed.

### Gotchas/Compatibility

For `GSON` and `RetroFit` compatibility check out [#121](https://github.com/Raizlabs/DBFlow/issues/121).

Due to this library using a custom maven repo, to speed up build times when using this library,
you should run in `--offline` mode except for when updating dependencies. To enable
this setting in Android Studio, ensure the option is checked in:
`Preferences->Build,Executor,Deployment->Build Tools->Gradle->Offline Work`

## Pull Requests

I welcome and encourage all pull requests. It usually will take me within 24-48 hours to respond to any issue or request. Here are some basic rules to follow to ensure timely addition of your request:
  1. Match coding style (braces, spacing, etc.) This is best achieved using CMD+Option+L (Reformat code) on Mac (not sure for Windows) with Android Studio defaults.
  2. If its a feature, bugfix, or anything please only change code to what you specify.
   **DO NOT** do this: Ex: Title "Fixes Crash Related to Bug" includes other files that were changed without explanation or doesn't relate to the bug you fixed. Or another example is a non-descriptive title "Fixes Stuff".
  3. Pull requests must be made against ```develop``` branch.
  4. Have fun!


## Maintainers

[agrosner](https://github.com/agrosner) ([@agrosner](https://www.twitter.com/agrosner))

## Contributors

[wongcain](https://github.com/wongcain)

[mozarcik](https://github.com/mozarcik)

[mickele](https://github.com/mickele)

[intrications](https://github.com/intrications)

[mcumings](https://github.com/mcumings)

[ktzouno](https://github.com/ktzouno)
