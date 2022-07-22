# HTTP Utilities 

## Server Static Files

Momentum will look for static files inside the `templates` folder inside app directory.
So put all files inside `templates` directory for serving it.

```text
└── templates
    ├── index.html
    └── style.css

```

This files can be accessed on 
http://ip:port/index.html and http://ip:port/style.css.

Static files from subdirectories of templates can also be accessed. Like,

```text
└── templates
    └── css
        └── style.css
    └── js
        └── index.js

```

This files can be accessed on 
http://ip:port/css/style.css and http://ip:port/js/index.js.

## Send a Text Response

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      res.sendString('Momentum is up and running!');
  });

```

## Send a Json Response

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      res.sendJson({'blaa': 'bluu'});
  });

```

## Render a Html File

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      res.renderHTML('index.html');
  });

```

## Send a Html File with parameters

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      res.Template('index.html', {'title' : 'My Momentum App'});
  });

```


## Response headers

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      res.setHeaders([{'Content-Type':'application/json'}]);
      res.sendJson({'blaa': 'bluu'});
  });

```

## Send flash Messages

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
     res.flashMessage('success', 'Hey Momentum is up!!');
  });

```

## Cookies

### Set Cookies

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      res.setCookies('key', 'value');
  });

```
### Remove Cookies

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      res.removeCookies('key');
  });

```


### Clear Cookies

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      res.clearCookies();
  });

```

## Sessions

### Set Session

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      req.storeSession('key', 'value');
  });

```

### Get Session value

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      final sess = req.getSession(key);
      print(sess);
  });

```

### Clear Session

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      req.clearSession('key');
  });

```


## Get HTTP POST Body data 

```dart
<!-- Express Js way -->
import 'dart:convert';
import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      final data = await req.body();
      print(jsonDecode(data)['<key>']);
      // Will print a value for the supplied key
  });

```

## Get Query 

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res) async {
      final data = await req.query();
      print(data);
      // Will print a json data
  });

```

## Download a HTTP POST File 

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      req.DownloadFile();
  });

```

## Set Individual routes CORS

```dart
<!-- Express Js way -->

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      res.setCors(Methods: 'GET , POST', Origins: '*');
  });

```