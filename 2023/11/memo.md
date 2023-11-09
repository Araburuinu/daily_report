## VendingMachine クラス

### initialize(stock)
- 在庫の初期状態を設定する
- 売り上げの初期値を0に設定する

### restock(juice, count)
- ジュースのインスタンスと本数を指定して在庫を補充するメソッド

### process_order(order_juice, order_qty, deposit, suica)
- 引数
    - ジュースのインスタンス
    - ジュースの本数
    - 現在のチャージ残高
    - suicaのインスタンス
- 例外処理
    - 在庫が不足していたら例外を返す
    - Suicaの残高が不足していたら例外を返す
- 自販機の在庫の数を減らす
- 自販機の売上を増やす
- suicaインスタンスに支払い金額を渡して支払い処理を実行する

### インスタンス変数の参照メソッド
- stock 在庫
- sales 売り上げ

### private find_item_from_stock(item_name)
- ジュースのインスタンスを引数に、在庫から該当するハッシュを返す

### private update_sales(cash)
- 売上を更新する

## Suica クラス

### initialize
- デポジットの初期値を設定し、初期チャージをセットする

### charge(cash)
- 100円未満の入金の場合例外を返す
- 100円以上の入金の場合、デポシットを増やす。

### make_payment(cash)
- プライベートメソッドのprocess_payment(cash)を実行する

### インスタンス変数の参照メソッド
- deposit デポジット

### private process_payment(cash)
- 購入分だけデポジットを減らす