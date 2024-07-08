## 推特留言情緒分類：比較 Word2Vec 和 Bert 表現

為了增進在 NLP 相關技術的熟練應用程度，我在 Kaggle 上找了一個推特留言的資料集：

- 名稱：[Sentiment140 dataset with 1.6 million tweets](https://www.kaggle.com/datasets/kazanova/sentiment140)
- 描述：包含用戶資料、推特留言和情緒等欄位，總共有 160000 筆，其中標註為 positive 和 negative 的資料各 80000 筆

### 程式碼

1. 資料集前處理：String Lowercase、Remove Punctuation、Word Tokenization、Remove Stop Word、Remove Meaningless Word、Word Lemmatization

2. 切割資料集：`test_size = 0.3`，`random state = 0`

3. Word2Vec：使用 Gensim 套件

4. Bert：使用 Transformers 套件

### 結果

|模型|準確率|執行時間|
|-|-|-|
|Word2Vec|0.75|短|
|Bert|0.8|極長|

### 分析

我認為 Bert 因為考量到句子中每一個單詞前後文的語意關係，因此在理解上的表現比 Word2Vec 還要好，不過由於使用 Dense Vector 的關係，它所需要的執行時間比 Word2Vec 還要長了十數倍
