import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: MainPage(),
    );
  }
}

class MainPage extends StatefulWidget {
  const MainPage({super.key});

  @override
  State<MainPage> createState() => _MainPageState();
}

class _MainPageState extends State<MainPage> {
  var str = "Nothing clicked.";
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(
          "Buttons",
          style: GoogleFonts.rubik(
            fontSize: 20.0,
          ),
        ),
      ),
      floatingActionButtonLocation: FloatingActionButtonLocation.endFloat,
      floatingActionButton: FloatingActionButton(
        // mini: true,
        backgroundColor: Colors.red,
        onPressed: () {
          setState(() {
            str = "Floating action button clicked!";
          });
        },
        child: const Icon(Icons.add),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(
              str,
            ),
            const SizedBox(
              height: 10.0,
            ),
            ElevatedButton(
              style: ElevatedButton.styleFrom(
                // side: const BorderSide(
                //   color: Colors.blue,
                //   width: 3.0,
                // ),
                elevation: 20.0,
                primary: Colors.green,
              ),
              onPressed: () {
                setState(() {
                  str = "Download button clicked!";
                });
              },
              child: Row(
                mainAxisSize: MainAxisSize.min,
                children: [
                  const Icon(
                    Icons.save_alt_rounded,
                  ),
                  const SizedBox(
                    width: 5.0,
                  ),
                  Text(
                    "Download",
                    style: GoogleFonts.rubik(
                      fontSize: 20.0,
                    ),
                  )
                ],
              ),
            ),
            const SizedBox(
              height: 10.0,
            ),
            TextButton(
              style: TextButton.styleFrom(),
              onPressed: () {
                setState(() {
                  str = "Text button clicked!";
                });
              },
              child: Text(
                "Ok",
                style: GoogleFonts.rubik(
                  fontSize: 20.0,
                ),
              ),
            ),
            ButtonBar(
              alignment: MainAxisAlignment.center,
              children: [
                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      str = "Yes button clicked!";
                    });
                  },
                  child: Row(
                    children: [
                      Text(
                        "Yes",
                        style: GoogleFonts.rubik(
                          fontSize: 20.0,
                        ),
                      ),
                    ],
                  ),
                ),
                TextButton(
                  onPressed: () {
                    setState(() {
                      str = "No button clicked!";
                    });
                  },
                  child: Text(
                    "No",
                    style: GoogleFonts.rubik(
                      fontSize: 20.0,
                    ),
                  ),
                ),
              ],
            ),
            MaterialButton(
              elevation: 20.0,
              shape: RoundedRectangleBorder(
                side: const BorderSide(
                  color: Colors.blue,
                  width: 3.0,
                ),
                borderRadius: BorderRadius.circular(
                  10.0,
                ),
              ),
              onPressed: () {
                setState(() {
                  str = "Material button clicked!";
                });
              },
              color: Colors.yellow,
              textColor: Colors.blue,
              child: Text(
                "Enter",
                style: GoogleFonts.rubik(
                  fontSize: 20.0,
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
