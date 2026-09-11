# Lab 2 の追加課題（オプション）

* **Lab 2 が終わった後に時間があればチャレンジしてください。**

---
### 課題

* Notebook 環境で
* **Lab 2 で作成した Web検索ツールやロギング設定を再利用します。**
* 基盤モデルは、下記を使用します。
    - `amazon.nova-lite-v1:0`
      
---

###　手順 

1. Lab 2 の最後のセルで、Code Cell を追加します。
<img width="298" height="66" alt="add_code_cell" src="https://github.com/user-attachments/assets/34cd7b36-ac4b-476b-89cf-bf0f1a21ef00" />

1. 下記のコードを貼り付けます。

    ```
    # TODO 旅行観光アドバイザーエージェントを作成
    
    
    
    print("私は TravelBot という、役立つ旅行の観光アドバイザーです。観光についてのお問い合わせに対応します。\n")
    
    flag = True
    
    while flag:
        prompt = input("prompt>")
        
        if prompt == "quit":
            flag = False
        else:
           # TODO 観光アドバイザーをテストする
    
           # TODO レスポンスを表示
            
    print("チャットボットを終了しました。\n")
    ```

1. コードの中で **TODO** と記載された部分に必要なコードを追加します。

1. 下記のような問い合わせを行い、動作を確認します。
    - `京都の有名な観光地を3つ挙げて下さい。`
    - `京都駅から金閣寺に行くにはどうすればいいですか？` 
---

1. 解答例

    ```
    # TODO 旅行観光アドバイザーエージェントを作成
    recipe_agent = Agent(callback_handler=None,
        model="amazon.nova-lite-v1:0",
        system_prompt="""あなたは TravelBot という旅行の観光アドバイザーです。
        ユーザーの旅行における観光地を見つけるのを手伝うために、観光地に関する質問に答えてください。
        観光地の情報を探すには websearch ツールを使用してください。""",
        tools=[websearch]
    )
    
    
    print("私は TravelBot という、役立つ旅行の観光アドバイザーです。観光についてのお問い合わせに対応します。\n")
    
    flag = True
    
    while flag:
        prompt = input("prompt>")
        
        if prompt == "quit":
            flag = False
        else:
           # TODO 観光アドバイザーをテストする
           response = recipe_agent(prompt)
           # TODO レスポンスを表示
           print(response)
            
    print("チャットボットを終了しました。\n")
    ```
