# Inaka's Android Development Guidelines

## Code Conventions
Android projects are Java projects, so they must follow the well-known code conventions for the Java programming languages. These are easily available online so look for them and apply them to the projects.

In our projects we use Android Lint with an extension called [Lewis](https://github.com/inaka/lewis) to check our code, there we add some rules like:
* Every .java file must be inside a custom package, not inside the root package.
* Every application must have at least one launcher activity.
* Every application must have only one launcher activity.
* Every library must not have a launcher activity.
* Every library must not have icons.
* Every library must not use permissions.
* Every instance variable must be named beginning with 'm' and using camelCase (Exceptions: model classes, dependecies injection).
* Every class constant (static and final) must be named using UPPER_SNAKE_CASE.
* A string cannot be hardcoded inside layouts or menus. Now this is and error, not a warning.
* Every id inside layouts or menus must be named using lowerCamelCase.


## Other rules and recommendations

#### .gitignore file format
Minimum of things that must not be uploaded for each Android project:
```txt
.gradle 
/local.properties 
/.idea/ 
.DS_Store 
/build 
/captures
```
 In addition, be careful uploading `.iml` files, at most projects those files are not necessary and should be added to the .gitignore.


#### Code format and unused imports
Always keep a correct code format (indentation, spaces, etc) and avoid unused imports using Android Studio's shortcut `Command+Option+L` (in Mac).


#### File's header
Delete default header, avoid use headers to indicate only the creator of the file and the date. Add a header only if you want to explain the `purpose` of that file/class.


#### Documentation
Use always `JavaDoc` and avoid warnings.


#### Naming convention for widgets
Widgets id: contextName + name + widgetType (all camel case). For example: "loginNameTextView".


#### Persistent data locally
Put every SharedPreference inside the same unique file. Or, at least put those different files inside the same package (could be named “preferences” for example).
The same for DB (SQLite, Realm, etc), the package could be named “db” for example.


#### Use build flavors
Use build flavors to work with more than one environment (for example: dev, staging, production).


#### Observers
Use observers only when is strongly necessary and avoid their concatenation.


#### Testing
Use always `JUnit`, try to test most of algorithmic stuff and be careful testing UI behaviour.


#### Libraries development
* No launcher activities.
* No icons.
* No permissions inside AndroidManifest.xml.
* Tests and examples with clear code and documentation.
* A project using it (could be inside the same repo or not but in a different module).
* Use `JitPack.io` to allow include it via gradle.
[How to use JitPack.io](https://jitpack.io/docs/ANDROID/)

Examples: [TinyTask](https://github.com/inaka/TinyTask), [KillerTask](https://github.com/inaka/KillerTask).


