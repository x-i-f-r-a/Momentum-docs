# Templating 

Currently there is no officially supported template engine for Momentum Web Framework. You can use third-party template engines like [Liquid Engine](https://pub.dev/packages/liquid_engine) , [Jaded](https://pub.dev/packages/jaded) , [Mustache](https://pub.dev/packages/mustache).etc. But they aren't recommended for production usage. 

For passing data to webpage you can use,

## Variable Values

```dart

//main.dart

import 'package:momentum_web/momentum_web.dart';


class App {
  void main({server}) async {

                
    final app = Momentum();


    app.GET('/', (Request req,Response res){


      res.Template('index.html', {'title':'My Moment'});
      

    });

    

    await app.runServer(host: '127.0.0.1', port: 8000);

  }
}

```



```html

<!-- index.html -->

<!DOCTYPE html>
    <html lang="en">
    <head>
    <title>#title</title>
    </head>
    <body>
        This is my moment...
    </body>
</html>


```

## Using for Loop


### Looping values of a list using dart


```dart

//main.dart

import 'package:momentum_web/momentum_web.dart';
import 'index.html.dart';

class App {
  void main({server}) async {

                
    final app = Momentum();


    app.GET('/', (Request req,Response res){


      res.HTML(index({'list': ['user1', 'user2']}));
      

    });

    

    await app.runServer(host: '127.0.0.1', port: 8000);

  }

}
```



```dart

// index.html.dart


String temp(data){
  return '<h3>$data</h3>';
}

var index = (Map<String, dynamic> data)=>
    """
    <html>
    <head>
        <title>My Moment..</title>
    </head>
    <body>
        <div>${data['list'].map(temp).join()}</div>
    </body>
  


    """;




```


