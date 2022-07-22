# Architecture Support

Momentum web framework support two type of architecture for developing web applications.

## Express Js Architecture

For the developers from Javascript and for the developers who are developing small API's or websites , Momentum support Express Js type developing architecture.

#### Example 

```dart

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', (Request req, Response res){
      res.sendString('Momentum is up and running');
 });

}


```
Or Go's Fiber like

```dart

import 'package:Momentum/momentum.dart';

void main() async {
  final app = Momentum();


  app.GET('/', Home);


  Future Home(Request req, Response res){
      res.sendString('Momentum is up and running');
 };

}

```


## Laravel like MVC Architecture


For the web artisans , momentum support separating logic and view. 
The `Controllers` folder contains the sample program to write a separate class with functions and it can be called inside our main `main.dart` file.


