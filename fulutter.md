## 2-1 プロジェクトの構成
### プロジェクトのファイル構成
#### プロジェクトのフォルダ類
- .dart_tool
- .idea
- build
- android
- ios
- linux
- macOS
- windows
- web
- lib
- test
### アプリ実行の仕組み
```
void main() {
    runApp( ウィジェット );
}
```
### StatelessWidgetクラス
```
class クラス名 extends StatelessWidget {

    @override
    Widget build(BuildContext context) {
        return MaterialApp(--略--);
    }
}
```
### MaterialAppクラス
```
return MaterialApp(
    title: 'Flutter Demo',
    home: Text(
        'Hello, Flutter World!!',
        style: TextStyle(fontSize:32.0),
    ),
);
```
### Scaffold
```
Scaffold(appBar:〇〇, body:〇〇)
```
### appBarとAppBarクラス
```
appBar: AppBar(
    title: Text('Hello Flutter!'),
),
```
### bodyについて
```
body: Text(
    'Hello Flutter World!!',
    style: TextStyle(fontSize:32.0),
),
```
### StatefulWidgetとState
#### StatefulWidgetクラスの基本形
```
class ウィジェットクラス extends StatefulWidget {

    @override
    ステートクラス createState() => ステートクラス();
}
```
#### Stateクラスの基本形
```
class ステートクラス extends State<ウィジェットクラス> {

    --略--

    @override
    Widget build(BuildContext context) {
        --略--
    }
}
```
### ステートクラスとの連携
```
@override
_MyHomePageState createState() => _MyHomePageState();
```
### ステート更新とsetState
```
void _setMessage() {
    setState((){
        _message = 'タップしました！';
    });
}
```
### FloatingActionButtonクラスについて
```
floatingActionButton: FloatingActionButton(
    onPressed: _steMassage,
    tooltip: 'set massage',
    child: Icon(Icons.star),
),
```
### Dataクラス
```
class Date {
    int _price;
    String _name;

    Date(this._name, this._price): super();

    @override
    String toString() {
        return _name + ':' + _price.toString() + '円';
    }
}
```
### Dataインスタンスの設定
```
static final _data = [
    Data('Apple', 200),
    Data('Orange', 150),
    Data('Peach', 300),
];
Data _item;
```
## 2-3 ウィジェットの基本レイアウト
### Colorについて
```
color: const Color(0xff000000),

Color.fromARGB(アルファ, 赤, 緑, 青)
```
### Centerクラスの基本形
```
Center(
    child: --ウィジェット--
)
```
### Containerクラスの基本形
```
Container(
    child: --ウィジェット--,
    padding: <EdgeInsets>,
    alignment: <Alignment>,
)
```
## 2-4 複数ウィジェットの配置
### Columnの基本形
```
Column(
    mainAxisAlignment: [MainAxisAlignment],
    mainAxisSize: [MainAxisSize],
    crossAxisAlignment: [CrossAxisAlignment],
    children: <Widget>[--リスト--]
)
```
## 3-1 ボタン・ウィジェット
### TextButtonの基本形
```
TextButton(key:null,
    onPressed: 関数,
    child: ウィジェット
)
```
### アイコンを表示する
```
TextButton(
    onPressed:buttonPressed,
    child: Padding(
        padding: EdgeInsets.all(10.0),
        child:Icon (
            Icons.android,
            size: 50.0,
        )
    )
)
```
### Paddingについて
```
children: <Widget>[
    Padding(
        padding: EdgeInsets.all(20.0),
        child: Text(----),
        TextButton(
            onPressed: buttonPressed,
            child: Padding(
                padding: EdgeInsets.all(10.0),
                    child: Text(----)
            )
        )
    )
]
```
## 3-2 入力のためのUI
### TextFieldとController
```
TextField(
    controller:<TExtEditingController>,
    style:<TExtStyle>
)
```
### Checkboxの基本
```
Checkbox(
    value: <bool>,
    onChanged: 関数,
),
```
```
void checkChanged(bool? value) {
    setStart(() {
        _checked = value!;
        _message = value ? 'checked!' : 'not checked...';
    });
}
```
### Radioの値の仕組み
```
Radio<型>(
    value: 値,
    groupValue: 値,
    onChanged:--メソッド--,
)
```
```
Radio<String>(
    value: 'A',
    groupValue: _selected,
    onChanged: checkChanged,
),
```
### DropdownButtonの基本形
```
DropdownButton<型>(
    onChanged: 関数,
    value: 値,
    style: <TextStyle>,
    items: [<DropdownMenuItem>,----]
)
```
### DropdownMenuItemについて
```
DropdownMenuItem<型>(value: 値, child: ウィジェット)
```
### Sliderの基本形
```
Slider(
    onChanged: 関数,
    min:<double>,
    max:<double>,
    divisions:<int>,
    value:<double>,
),
```