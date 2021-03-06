# Test package

* Access to package with this [link](https://pub.flutter-io.cn/packages/test)

## Useful functions

* Test assertions are made using [expect()](https://pub.flutter-io.cn/documentation/test_api/latest/test_api/expect.html)

* Tests can be grouped together using the [group()](https://pub.flutter-io.cn/documentation/test_api/latest/test_api/group.html) function.

* You can use the [setUp()](https://pub.flutter-io.cn/documentation/test_api/latest/test_api/setUp.html) and [tearDown()](https://pub.flutter-io.cn/documentation/test_api/latest/test_api/tearDown.html) functions to share code between tests.

## Test Exception

### To simply test that an unspecific exception is raised

``` dart
expect(() => range(5, 5), throwsException);
```

### To test that the right type of exception is raised:

``` dart
expect(() => range(5, 2), throwsA (TypeMatcher<IndexError>()));
```

### To ensure that no exception is raised:

``` dart
expect(() => range(5, 10), returnsNormally);
```

### To test the exception type and exception message:

``` dart
expect(() => range(5, 3), throwsA(predicate((e) => e is ArgumentError && e.message == 'start must be less than stop')));
```

Refer to [stack overflow](https://stackoverflow.com/questions/13298969/how-do-you-unittest-exceptions-in-dart) for more information.