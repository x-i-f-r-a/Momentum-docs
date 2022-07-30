# JWT

JWT authentication can be setup by using [dart_jsonwebtoken](https://pub.dev/packages/dart_jsonwebtoken) package. Its pub.dev homepage have good documentation to how to use it.

## Signing

```dart
// Create a json web token
final jwt = JWT(
  {
    'id': 123,
    'server': {
      'id': '3e4fc296',
      'loc': 'euw-2',
    }
  },
  issuer: 'https://github.com/jonasroussel/dart_jsonwebtoken',
);

// Sign it (default with HS256 algorithm)
token = jwt.sign(SecretKey('secret passphrase'));

print('Signed token: $token\n');

```

## Verifying


```dart

try {
  // Verify a token
  final jwt = JWT.verify(token, SecretKey('secret passphrase'));

  print('Payload: ${jwt.payload}');
} on JWTExpiredError {
  print('jwt expired');
} on JWTError catch (ex) {
  print(ex.message); // ex: invalid signature
}

```