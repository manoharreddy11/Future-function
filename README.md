import 'package:flutter/material.dart';

class MyWidget extends StatelessWidget {
  Future<int> computeSum(List<int> numbers) {
    return Future.delayed(Duration(seconds: 2), () {
      int sum = numbers.reduce((value, element) => value + element);
      return sum;
    });
  }

  @override
  Widget build(BuildContext context) {
    List<int> numbers = [1, 2, 3, 4, 5];
    print('Computing sum...');

    computeSum(numbers).then((value) {
      print('Sum of numbers: $value');
    });

    print('Sum computation request initiated.');

    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Future Example')),
        body: Center(child: Text('Check for output')),
      ),
    );
  }
}

void main() {
  runApp(MyWidget());
}
