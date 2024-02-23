                                                 👇👇 --> Sample App <-- 👇👇
void main() {
  runApp(const MyApp());
}



class MyApp extends StatelessWidget{
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {

    return MaterialApp(  // (ctrl + p) click kore ki ki kora jai dekha jabe
        theme: ThemeData(primarySwatch: Colors.green),
        darkTheme: ThemeData(primarySwatch: Colors.blueGrey),
        color: Colors.indigo,
        debugShowCheckedModeBanner: false,
        home:HomeActivity()    // click -->  ctrl + P

    );
  }
}



class HomeActivity extends StatelessWidget{
  const HomeActivity({super.key});

  // for code low complexity
  MySnackBar(message,context){

    return ScaffoldMessenger.of(context).showSnackBar(
      SnackBar(content: Text(message))
    );
  }


  @override
  Widget build(BuildContext context) {

    // scaffold er vitore whole screen a ja thakbe tai thakbe
    return Scaffold(  //(ctrl + p) use kore ki ki kora jai dekha jabe
      appBar: AppBar(
        title: Text("My Flutter App"),
        //titleSpacing: 90,
        centerTitle: true,
        toolbarHeight: 60,
        toolbarOpacity: 1,
        elevation: 8,
        backgroundColor: Colors.indigo,
        actions: [
          IconButton(onPressed: (){MySnackBar("Iam Search", context);}, icon: Icon(Icons.search)),
          IconButton(onPressed: (){MySnackBar("Iam Comment", context);}, icon: Icon(Icons.comment)),
          IconButton(onPressed: (){MySnackBar("Iam Setting", context);}, icon: Icon(Icons.settings)),
          IconButton(onPressed: (){MySnackBar("Iam Email", context);}, icon: Icon(Icons.email)),
        ],
      ),
      floatingActionButton: FloatingActionButton(
        elevation: 10,
      child: Icon(Icons.add),
      backgroundColor: Colors.indigo,
      onPressed: (){
          MySnackBar("Iam Floating Action Button", context);
      },
    ),
      bottomNavigationBar: BottomNavigationBar(
        currentIndex: 0,
        items: [
          BottomNavigationBarItem(icon: Icon(Icons.home),label: "Home"),
          BottomNavigationBarItem(icon: Icon(Icons.message),label: "Contact"),
          BottomNavigationBarItem(icon: Icon(Icons.person),label: "Profile"),
        ],
        onTap: (int index){
          if(index==0){
            MySnackBar("Iam Home bottom menu", context);
          }
          if(index==1){
            MySnackBar("Iam contact bottom menu", context);
          }
          if (index==2){
            MySnackBar("Iam Profile bottom menu", context);
          }
        },
      ),


    );
  }
}
