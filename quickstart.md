## Quick Start 

### Prerequisites 

In order to use Momentum Web Framework you must have the [Dart SDK][dart_installation_link] installed on your machine.


Momentum requires Dart `">=2.17.0 <3.0.0"`


### Installing Momentum CLI Tool 

```shell
#  Install the moment cli from pub.dev

dart pub global activate mcli

```

### Creating a New Project 

Use the `mcli create <project name>` command to create a new project.

```shell
#  Create a new project called "MyDreamProject"
mcli create MyDreamProject
```

The directory structure is as follows:

```text
MyDreamProject
└── templates
    └── Home_view.dart
└── Controllers
    └── Home.dart
├── pubspec.yaml
├── main.dart
└── isolator.dart
```

### Start the Development Server

Next, open the newly directory of created project and start the dev server by:

```shell
#  Start the development server
mcli dev
```


By default port `80` is used. A custom port can be used inside the app's port option.




[dart_installation_link]: https://dart.dev/get-dart