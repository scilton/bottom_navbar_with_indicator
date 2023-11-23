<!--
This README describes the package. If you publish this package to pub.dev,
this README's contents appear on the landing page for your package.

For information about how to write a good package README, see the guide for
[writing package pages](https://dart.dev/guides/libraries/writing-package-pages).

For general information about developing packages, see the Dart guide for
[creating packages](https://dart.dev/guides/libraries/create-library-packages)
and the Flutter guide for
[developing packages and plugins](https://flutter.dev/developing-packages).
-->


# bottom_navbar_with_indicator

A fully customizable bottom navigation bar with line indicators and gradient.

<div style="display:flex">
<img width="355" alt="alert2" src="https://github.com/hello-addweb/-TikTok-Flutter/assets/133627084/21647e09-5711-4704-80f8-4e8e84e781c7" width="200">
<img width="355" alt="alert2" src="https://github.com/hello-addweb/-TikTok-Flutter/assets/133627084/3ad5edf5-b81e-4b1f-8cfe-f4189268cbb7" width="200">
<div/>

<b>Usage without gradient: </b>

            class MyExample extends StatefulWidget {
            @override
            _MyExampleState createState() => _MyExampleState();
            }

            class _MyExampleState extends State<MyExample> {
            int _selectedIndex = 0; //default index

            List<Widget> _widgetOptions = [
                Text('Home'),
                Text('Account'),
                Text('Leaves'),
                Text('Loyalty'),
                Text('Requests'),
            ];
            @override
            Widget build(BuildContext context) {
                return Scaffold(
                appBar: AppBar(
                    title: Text('Example'),
                ),
                body: Center(
                    child: _widgetOptions.elementAt(_selectedIndex),
                ),
                bottomNavigationBar: CustomLineIndicatorBottomNavbar(
                    selectedColor: Colors.blue,
                    unSelectedColor: Colors.black54,
                    backgroundColor: Colors.white,
                    currentIndex: _selectedIndex,
                    onTap: (index) {
                    setState(() {
                        _selectedIndex = index;
                    });
                    },
                    enableLineIndicator: true,
                    lineIndicatorWidth: 3,
                    indicatorType: IndicatorType.Top,
                    // gradient: LinearGradient(
                    //   colors: kGradients,
                    // ),

                    customBottomBarItems: [
                    CustomBottomBarItems(
                        label: 'Home',
                        icon: Icons.home,
                    ),
                    CustomBottomBarItems(
                        label: 'Account',
                        icon: Icons.account_box_outlined,
                    ),
                    CustomBottomBarItems(
                        label: 'Leaves', icon: Icons.calendar_today_outlined),
                    CustomBottomBarItems(
                        label: 'Loyalty',
                        icon: Icons.card_giftcard_rounded,
                    ),
                    CustomBottomBarItems(
                        label: 'Requests',
                        icon: Icons.list,
                    ),
                    ],
                ),
                );
            }
            }

<b>Usage with gradient : </b>

    class MyExample extends StatefulWidget {

        @override
        _MyExampleState createState() => _MyExampleState();
    }

    class _MyExampleState extends State<MyExample> {
        int _selectedIndex = 0; //default index

        List<Widget> _widgetOptions = [
            Text('Home'),
            Text('Account'),
            Text('Leaves'),
            Text('Loyalty'),
            Text('Requests'),
        ];
        @override
        Widget build(BuildContext context) {
        return Scaffold(
            appBar: AppBar(
                title: Text('Example'),
            ),
            body: Center(
                child: _widgetOptions.elementAt(_selectedIndex),
            ),
            bottomNavigationBar: CustomLineIndicatorBottomNavbar(
            selectedColor: Colors.white,
            unSelectedColor: Colors.black54,
            backgroundColor: Colors.white,
            currentIndex: _selectedIndex,
            onTap: (index) {
                setState(() {
                _selectedIndex = index;
                });
            },
            enableLineIndicator: true,
            lineIndicatorWidth: 3,
            indicatorType: IndicatorType.Top,
            gradient: LinearGradient(
                colors: [Colors.pink, Colors.yellow],
            ),
            customBottomBarItems: [
                CustomBottomBarItems(
                    label: 'Home',
                    icon: Icons.home,
                ),
                CustomBottomBarItems(
                    label: 'Account',
                    icon: Icons.account_box_outlined,
                ),
                CustomBottomBarItems(
                    label: 'Leaves', icon: Icons.calendar_today_outlined),
                CustomBottomBarItems(
                    label: 'Loyalty',
                    icon: Icons.card_giftcard_rounded,
                ),
                CustomBottomBarItems(
                    label: 'Requests',
                    icon: Icons.list,
                ),
            ],
            ),
        );
        }
    }
    