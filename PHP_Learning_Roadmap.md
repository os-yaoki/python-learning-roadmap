# 🐘 PHP言語 初心者向け学習ロードマップ

サーバーサイド開発の入門言語として最適な PHPの効率的な学習ガイドです。

**WebアプリケーションやCMSの開発に必須なスキルを、3～4ヶ月で習得できます。**

---

## 📋 PHPとは？

| 項目 | 説明 |
|------|------|
| **用途** | Webサーバーで動く言語。Webサイトの動的な処理を行う |
| **特徴** | シンプルで学習しやすい、世界のWebサイト80%以上で使用 |
| **活用例** | WordPress、Facebook、メルカリなど大規模サービスも使用 |
| **将来性** | 今後も需要が高い。エンジニア転職に有利 |
| **年収** | 初級：月25～35万円 / 中級：月35～50万円 / シニア：月50～70万円 |

---

## 📚 段階別学習ロードマップ

### **段階1：環境構築と基本概念（2～3日）**

#### **最初にやることは2つ：**

**1. PHPの実行環境を整える**

最も簡単な方法：**XAMPP のインストール**
- Windows/Mac/Linux対応
- Apache（Webサーバー）とMySQL（データベース）が一緒に入っている
- インストール後、すぐにPHPが使える

```
XAMPP をダウンロード → インストール → Apache を起動
```

**2. 最初のコードを書く**

`C:\xampp\htdocs\test.php` に以下を保存：

```php
<?php
    echo "Hello, PHP!";
    echo 10 + 20;
?>
```

ブラウザで `http://localhost/test.php` を開く → 画面に「Hello, PHP!30」と表示される

**学習時間：** 1～2日で十分

**学習リソース：**
- XAMPP公式ドキュメント
- YouTube「XAMPP インストール」

---

### **段階2：基本文法（2～3週間）**

Pythonに似ていますが、PHPならではの特徴もあります。

#### **学ぶべき基礎項目：**

| 項目 | 重要度 | 学習時間 | ポイント |
|------|--------|---------|---------|
| 変数とデータ型 | ⭐⭐⭐⭐⭐ | 3日 | $ で始まる変数、型の自動変換 |
| 演算子と条件分岐 | ⭐⭐⭐⭐⭐ | 3日 | if 文、switch 文など |
| ループ処理 | ⭐⭐⭐⭐⭐ | 3日 | for, while, foreach など |
| 関数 | ⭐⭐⭐⭐⭐ | 4日 | 関数定義、組み込み関数 |
| 配列 | ⭐⭐⭐⭐⭐ | 4日 | 配���の操作、連想配列 |

#### **実践コード例：**

```php
<?php
// 1. 変数とデータ型
$name = "太郎";
$age = 25;
$height = 170.5;

echo $name . "は" . $age . "歳です<br>";

// 2. 条件分岐
if ($age >= 20) {
    echo "成人です<br>";
} else {
    echo "未成年です<br>";
}

// 3. ループ処理
for ($i = 1; $i <= 5; $i++) {
    echo $i . "<br>";
}

// 4. 関数定義
function add($a, $b) {
    return $a + $b;
}

echo add(5, 3);  // 8

// 5. 配列
$fruits = array("りんご", "みかん", "バナナ");
echo $fruits[0];  // りんご

// 6. 連想配列（キーと値のペア）
$person = array(
    "name" => "太郎",
    "age" => 25,
    "city" => "東京"
);

echo $person["name"];  // 太郎
?>
```

**学習リソース：**
- 📺 YouTube「PHP 基本文法」シリーズ
- 📖 Progate「PHP I」コース
- 💻 PHP公式ドキュメント

---

### **段階3：HTMLフォームとの連携（2週間）**

PHPの本当の力は、**HTMLフォームからデータを受け取ること**です。

#### **学ぶべき項目：**

| 項目 | 重要度 | 学習時間 | 学習内容 |
|------|--------|---------|---------|
| GET と POST の違い | ⭐⭐⭐⭐⭐ | 2日 | フォームデータの送受信方法 |
| $_GET と $_POST | ⭐⭐⭐⭐⭐ | 2日 | フォームデータを受け取る |
| $_REQUEST | ⭐⭐⭐⭐ | 1日 | GETとPOSTの両方を処理 |
| フォーム検証 | ⭐⭐⭐⭐ | 2日 | 入力データのチェック |
| セッション管理 | ⭐⭐⭐⭐⭐ | 2日 | ユーザー情報を保持する |

#### **実践コード例：**

**HTMLフォーム（form.html）:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>簡単なフォーム</title>
</head>
<body>
    <h1>情報入力</h1>
    <form method="POST" action="process.php">
        <label>名前: <input type="text" name="name"></label><br>
        <label>年齢: <input type="number" name="age"></label><br>
        <button type="submit">送信</button>
    </form>
</body>
</html>
```

**PHPでデータを処理（process.php）:**
```php
<?php
// POSTメソッドで送信されたデータを受け取る
$name = $_POST["name"];
$age = $_POST["age"];

echo "名前: " . $name . "<br>";
echo "年齢: " . $age . "<br>";

// 条件分岐
if ($age >= 20) {
    echo "成人です<br>";
} else {
    echo "未成年です<br>";
}
?>
```

**セッション管理の例：**
```php
<?php
// セッションを開始
session_start();

// ログイン情報をセッションに保存
$_SESSION["user_name"] = "太郎";
$_SESSION["user_id"] = 123;

// 別のページでセッション情報を使用
echo $_SESSION["user_name"];  // 太郎
?>
```

---

### **段階4：データベース（MySQL）連携（3～4週間）**

PHPの真の力はデータベースと組み合わせた時に発揮されます。

#### **学ぶべき項目：**

| 項目 | 重要度 | 学習時間 | 学習内容 |
|------|--------|---------|---------|
| SQL の基本（SELECT, INSERT, UPDATE, DELETE） | ⭐⭐⭐⭐⭐ | 3日 | データベースクエリの基本 |
| MySQLの接続（mysqli）| ⭐⭐⭐⭐⭐ | 2日 | PHPからデータベースに接続 |
| データの取得 | ⭐⭐⭐⭐⭐ | 2日 | SELECT で データを取り出す |
| データの挿入 | ⭐⭐⭐⭐⭐ | 2日 | INSERT でデータを保存 |
| データの更新・削除 | ⭐⭐⭐⭐ | 2日 | UPDATE, DELETE |
| PDO（推奨） | ⭐⭐⭐⭐ | 3日 | より安全なデータベース操作 |

#### **実践コード例：**

**データベースに接続:**
```php
<?php
// MySQLに接続
$servername = "localhost";
$username = "root";
$password = "";  // XAMPPではデフォルトで空
$dbname = "my_database";

$conn = new mysqli($servername, $username, $password, $dbname);

// 接続チェック
if ($conn->connect_error) {
    die("接続失敗: " . $conn->connect_error);
}

echo "接続成功!";
?>
```

**データを取得（SELECT）:**
```php
<?php
$conn = new mysqli("localhost", "root", "", "my_database");

// テーブルからデータを取得
$sql = "SELECT * FROM users";
$result = $conn->query($sql);

// 結果をループで表示
while ($row = $result->fetch_assoc()) {
    echo "名前: " . $row["name"] . "<br>";
    echo "年齢: " . $row["age"] . "<br>";
    echo "---<br>";
}

$conn->close();
?>
```

**データを挿入（INSERT）:**
```php
<?php
$conn = new mysqli("localhost", "root", "", "my_database");

$name = $_POST["name"];
$age = $_POST["age"];
$city = $_POST["city"];

// INSERT文を実行
$sql = "INSERT INTO users (name, age, city) VALUES ('$name', $age, '$city')";

if ($conn->query($sql) === TRUE) {
    echo "データが保存されました!";
} else {
    echo "エラー: " . $conn->error;
}

$conn->close();
?>
```

**⚠️ SQL インジェクション対策（PDOを使う）:**
```php
<?php
$conn = new PDO("mysql:host=localhost;dbname=my_database", "root", "");

$name = $_POST["name"];
$age = $_POST["age"];

// プリペアドステートメント（安全）
$stmt = $conn->prepare("INSERT INTO users (name, age) VALUES (?, ?)");
$stmt->execute([$name, $age]);

echo "データが安全に保存されました!";
?>
```

---

### **段階5：小さなプロジェクト実装（3～4週間）**

ここまで学んだことを使って、実際に動くアプリを作ります。

#### **プロジェクト1：簡単なお問い合わせフォーム（1～2週間）**

```php
<?php
// contact.php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = htmlspecialchars($_POST["name"]);
    $email = htmlspecialchars($_POST["email"]);
    $message = htmlspecialchars($_POST["message"]);
    
    // メール送信
    $to = "admin@example.com";
    $subject = "お問い合わせ: " . $name;
    $body = "名前: " . $name . "\n";
    $body .= "メール: " . $email . "\n";
    $body .= "メッセージ: " . $message;
    
    mail($to, $subject, $body);
    
    echo "送信されました！";
} else {
?>
    <form method="POST">
        <label>名前: <input type="text" name="name" required></label><br>
        <label>メール: <input type="email" name="email" required></label><br>
        <label>メッセージ: <textarea name="message" required></textarea></label><br>
        <button type="submit">送信</button>
    </form>
<?php
}
?>
```

#### **プロジェクト2：ユーザー登録・ログインシステム（2～3週間）**

```php
<?php
// register.php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $conn = new mysqli("localhost", "root", "", "my_app");
    
    $username = htmlspecialchars($_POST["username"]);
    $email = htmlspecialchars($_POST["email"]);
    $password = password_hash($_POST["password"], PASSWORD_DEFAULT);
    
    $sql = "INSERT INTO users (username, email, password) VALUES (?, ?, ?)";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("sss", $username, $email, $password);
    
    if ($stmt->execute()) {
        echo "登録成功！";
    } else {
        echo "登録失敗: " . $stmt->error;
    }
    
    $conn->close();
}
?>

<!-- ログイン部分 -->
<?php
// login.php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $conn = new mysqli("localhost", "root", "", "my_app");
    
    $email = htmlspecialchars($_POST["email"]);
    $password = $_POST["password"];
    
    $sql = "SELECT * FROM users WHERE email = ?";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("s", $email);
    $stmt->execute();
    $result = $stmt->get_result();
    
    if ($result->num_rows > 0) {
        $user = $result->fetch_assoc();
        
        // パスワードを検証
        if (password_verify($password, $user["password"])) {
            session_start();
            $_SESSION["user_id"] = $user["id"];
            $_SESSION["username"] = $user["username"];
            
            header("Location: dashboard.php");
            exit;
        } else {
            echo "パスワードが違います";
        }
    } else {
        echo "ユーザーが見つかりません";
    }
    
    $conn->close();
}
?>
```

#### **プロジェクト3：TODOリスト（データベース保存版）（2～3週間）**

```php
<?php
// todo.php
session_start();
$conn = new mysqli("localhost", "root", "", "my_app");

// タスク追加
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $task = htmlspecialchars($_POST["task"]);
    $user_id = $_SESSION["user_id"];
    
    $sql = "INSERT INTO tasks (user_id, task, completed) VALUES (?, ?, 0)";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("is", $user_id, $task);
    $stmt->execute();
}

// タスク削除
if (isset($_GET["delete"])) {
    $task_id = $_GET["delete"];
    $sql = "DELETE FROM tasks WHERE id = ?";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("i", $task_id);
    $stmt->execute();
}

// タスク取得
$user_id = $_SESSION["user_id"];
$sql = "SELECT * FROM tasks WHERE user_id = ? ORDER BY created_at DESC";
$stmt = $conn->prepare($sql);
$stmt->bind_param("i", $user_id);
$stmt->execute();
$result = $stmt->get_result();
?>

<h1>TODOリスト</h1>

<form method="POST">
    <input type="text" name="task" placeholder="新しいタスク" required>
    <button type="submit">追加</button>
</form>

<ul>
<?php
while ($row = $result->fetch_assoc()) {
    echo "<li>";
    echo $row["task"];
    echo " <a href='?delete=" . $row["id"] . "'>削除</a>";
    echo "</li>";
}
?>
</ul>

<?php $conn->close(); ?>
```

---

### **段階6：実務スキル習得（1～2ヶ月）**

より高度な内容を学んで、実務レベルへ。

#### **次に進むべき内容：**

| スキル | 重要度 | 学習時間 | 理由 |
|--------|--------|---------|------|
| **MVC フレームワーク** | ⭐⭐⭐⭐⭐ | 2～3週間 | 大規模プロジェクトの標準 |
| **Laravel（推奨）** | ⭐⭐⭐⭐⭐ | 2～3週間 | PHPで最も人気なフレームワーク |
| **セキュリティ対策** | ⭐⭐⭐⭐⭐ | 1～2週間 | SQL注入、XSS対策など |
| **API開発（REST API）** | ⭐⭐⭐⭐ | 2週間 | モダンなWeb開発 |
| **テストコード** | ⭐⭐⭐⭐ | 2週間 | プロダクション品質 |

---

## 📅 3ヶ月で習得する実際のスケジュール

| 時期 | 学習内容 | 毎日の時間 | 目標 |
|------|---------|---------|------|
| **週1-2** | 環境構築 + 基本文法 | 30分 | PHPコードをローカルで実行できる |
| **週3-4** | 条件分岐、ループ、関数 | 1時間 | 基本的なPHPプログラムが書ける |
| **週5-6** | HTMLフォーム連携 | 1時間 | フォームからデータを受け取れる |
| **週7-8** | SQL基礎 + MySQL接続 | 1.5時間 | データベースからデータ取得できる |
| **週9-12** | プロジェクト実装 | 1.5時間 | 登録・ログイン機能が実装できる |
| **週13+ | Laravel基礎** | 1.5時間 | フレームワークで効率よく開発できる |

---

## 💡 学習の黄金ルール

### **1. XAMPPで即座に実行する**
- ローカルサーバーを起動して、すぐに結果が見える
- ブラウザで http://localhost/ を見れば動作確認できる

### **2. HTMLとPHPを組み合わせる**
- PHPはサーバーサイド言語
- HTMLフォームでユーザーからデータを受け取る体験が大事

### **3. データベースと連携する**
- SQLを学ぶ前にPHPの基本文法を完璧にする必要はない
- 「実装しながら学ぶ」でいい

### **4. セキュリティを意識する**
- SQL注入、XSS対策は必須
- `htmlspecialchars()` や プリペアドステートメント を使う

### **5. 毎日30分以上、最低3ヶ月継続**
- 継続が全て

---

## 📚 学習リソース（優先度順）

| リソース | 料金 | 優先度 | 用途 |
|---------|------|--------|------|
| **Progate「PHP I・II」** | 月980円 | ⭐⭐⭐⭐⭐ | インタラクティブで初心者向け最高 |
| **PHP公式ドキュメント** | 無料 | ⭐⭐⭐⭐⭐ | 公式リファレンス |
| **YouTube「PHP 初心者」** | 無料 | ⭐⭐⭐⭐⭐ | わかりやすい動画 |
| **Udemy「完全初心者PHP」** | 1,500～2,500円 | ⭐⭐⭐⭐⭐ | コスパ最高 |
| **Laravel 公式ドキュメント** | 無料 | ⭐⭐⭐⭐ | フレームワーク学習用 |

---

## 🎓 学習中によくある落とし穴と対策

| 落とし穴 | 原因 | 対策 |
|---------|------|------|
| **「サーバーエラー」で止まる** | エラーメッセージが理解できない | error_reporting(E_ALL) で詳細を見る |
| **データベースに接続できない** | MySQLが起動していない | XAMPPコントロールパネルで起動確認 |
| **SQLインジェクション脆弱性** | セキュリティ意識が低い | プリペアドステートメントを使う |
| **フォームでデータが渡されない** | GETとPOSTの違いを理解していない | $_POSTと $_GET の使い分けを理解 |
| **パスワード保存が危険** | 平文保存している | password_hash() を使う |

---

## 💼 就職・転職への影響

PHPを習得すると：

- **初級エンジニア求人**：月給25～35万円（東京）
- **PHP + 基本的なセキュリティ**：月給30～45万円
- **Laravel / フレームワーク経験**：月給40～60万円
- **大規模プロジェクト経験**：年収500～800万円

**3ヶ月後にシンプルなアプリを作って見せれば、ジュニアエンジニアとしての採用可能性が高まります。**

---

## 🚀 最終的なアドバイス

**PHPを効率よく学ぶ秘訣は3つ：**

1. **XAMPPで即座に実行する** — ローカルサーバーで動作確認
2. **HTMLフォームから始める** — 「入力 → 処理 → 出力」の循環を体験
3. **毎日少しずつ継続する** — 1日2時間×2週間より1日30分×12週間

**今このチャンスに、PHPの世界に入ってください。** Webサイトの90%はPHPで動いています。あなたもその一員になれます。

**では、今日 XAMPPをインストールして、最初の「Hello, PHP!」をブラウザで見てくださいね！**

Happy Coding! 🐘✨
