## 講座で学んだこと
- Flutter Studioの操作

## 行ったこと
- p.140 ~ p.169
- chapter4-1 ~ chapter4-2

### AppBer
```
AppBar(
    title: ウィジェット,
    leading: ウィジェット,
    actions: <Widget>[ウィジェットのリスト],
    bottom: <PreferredSize>,
)
```
### BackButton
```
leading: BackButton(
    color: Colors.white,
),
```
### actionのアイコンについて
```
actions: <Widget>[
    IconButton(
        icon: Icon(Icons.android),
        tooltip: 'add star...',
        onPressed: iconPressedA,
    ),
    --省略--
],
```
### bottomの表示
```
bottom: PreferredSize(
    preferredSize: const Size.frommHeight(30.0),
    child: Center(
        child: Text(_stars,
            style: TextStyle(
                fontSize: 22.0,
                color: Colors.white,
            ),
        ),
    ),
),
```
### BottomNavigationBar
```
BottomNavigationBar(
    currentIndex: <int値>,
    items: <BottomNavigationBarItem>[リスト]
    onTap: 関数
)
```
### アイコンのカラーとサイズ
```
Icon(Icons.android,color: Colors.Black, size: 50)
```
### ListView
```
ListView(
    shrinkWrap: <bool値>,
    padding: <EdgeInsets>,
    children: <Widget>[リスト],
)
```
### ListTile
```
ListTile(
    leading:<Icon>,
    title: ウィジェット,
    selected: <bool値>,
    onTap: 関数,
    onLongPress: 関数
)
```
### SingleChildScrollView インスタンスの基本
```
SingleChildScrollView(
    child: ウィジェット
)
```
### 表示切り替えとナビゲーション
```
・移動先をpushする

Navigator.push(<BuildContext>,<Route>);

・移動をpopする

Navigator.pop(<BuildContext>);
```
### MaterialPageRoute
```
Navigator.push(
    context,
    MaterialPageRoute(builder: (context) => SecondScreen()),
);
```
### テキストによるルーティング
```
routes: {
    'アドレス': (context) => ウィジェット,
    'アドレス': (context) => ウィジェット,
    --必要なだけ記述--
}
```
### routesの定義
```
routes: {
    '/': (context) => FirstScreen(),
    '/second': (context) => SecondScreen('Second'),
    '/third': (context) => SecondScreen('Third'),
},
```
```
initialRoute: '/',
```
### pushNamedによる表示移動
```
Navigator.pushNamed(
    context,
    '/second',
);
```

## メモ
- chapter4まで重要!!
