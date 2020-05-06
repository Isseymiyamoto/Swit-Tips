# Swit-Tips
Swiftに関しての知見を集める

## Swift 文法

### 三項演算子

何らかの値に呼応して、2つの選択肢が考慮される場合に用いられる

```swift

// MARK: - how to use
    
    // 条件式 ? trueの時の処理 : falseの時の処理
    
// MARK: - example 

    var isFollowed: Bool = false
    isFollowed ? print("このユーザーにフォローされています") : print("このユーザーにはフォローされていません")
    // 出力: このユーザーにはフォローされていません 

```

## UIKitに関する情報

###  UILabel

UILabelに関する基本的な設定(よく使うプロパティ、関数など)

```swift

// MARK: Properties



```

### UIButton

UIButtonに関する基本的な設定(よく使うプロパティ、関数など)

```swift

// MARK: Properties

    let actionButton: UIButton = {
        // buttonタイプの決定
        let button = UIButton(type: .system)
        // 文字色やボーダー色など
        button.tintColor = .white
        // 背景色
        button.backgroundColor = .twitterBlue
        // タイトル・imageの設置
        button.setTitle("タイトル", for: .normal)
        button.setImage(UIImage(named: "new_tweet"), for: .normal)
        // actionハンドラの設定
        button.addTarget(self, action: #selector(actionButtonTapped), for: .touchUpInside)
        
        return button
    }()
    
// MARK: Lifecycle
    
    override func viewDidLoad(){
        super.viewDidLoad()
        
        任意の親View.addSubView(actionButton)
    
    }
    
// MARK: Selectors
    
    @objc func actionButtonTapped(){
        // buttonが押された際の挙動をここに書く
        print("buttonが押されました")
    }


```


## レイアウト

### frame

Viewのサイズや位置を決めるもの, 親Viewに対しての位置を指定する  
例えば下記では、view.addSubView(button)で親Viewはviewであるので、それに対してx方向0,y方向0に長さ100,200のbuttonを設置することになる

```swift

class frameController: UIViewController{

//MARK: - Properties

    let button: UIButton = {
        let button = UIButton(type: .system)
        button.setTitle("frameについて", for: .normal)
        button.frame = CGRect(x: 0, y: 0, width: 100, height: 200)
        return button
    }()

//MARK: - Lifecycle

    override func viewDidLoad(){
        super.viewDidLoad()
        
        view.addSubView(button)
    }
}


```

### bounds



