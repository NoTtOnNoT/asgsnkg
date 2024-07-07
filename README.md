import 'package:flutter/material.dart';

class LoginPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Login'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text(
              'Login to your account',
              style: TextStyle(fontSize: 20),
            ),
            SizedBox(height: 20),
            TextFormField(
              decoration: InputDecoration(labelText: 'Username'),
            ),
            TextFormField(
              obscureText: true,
              decoration: InputDecoration(labelText: 'Password'),
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: () {
                // Add login authentication logic here
              },
              child: Text('Login'),
            ),
          ],
        ),
      ),
    );
  }
}
import 'package:flutter/material.dart';

class DataSelectionPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Data Selection'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text(
              'Select data to check',
              style: TextStyle(fontSize: 20),
            ),
            // Add your data selection widgets here
          ],
        ),
      ),
    );
  }
}
dependencies:
  flutter:
    sdk: flutter
  signature_pad: ^4.0.0
import 'package:flutter/material.dart';
import 'package:signature_pad/signature_pad.dart';

class SignaturePage extends StatefulWidget {
  @override
  _SignaturePageState createState() => _SignaturePageState();
}

class _SignaturePageState extends State<SignaturePage> {
  SignaturePadController _controller = SignaturePadController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Signature Pad'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            SignaturePad(
              controller: _controller,
              width: 300,
              height: 200,
              backgroundColor: Colors.white,
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: () {
                // Handle saving or using the signature
                final signatureData = _controller.toPngBytes();
                // Add logic to save or use the signature data
              },
              child: Text('Save Signature'),
            ),
          ],
        ),
      ),
    );
  }
}