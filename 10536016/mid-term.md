## 說明

1. 答案直接寫在這個 `mid-term.md` 裡，並使用 Markdown 語法撰寫。
1. 題目總共分 Ruby、Rails 以及 Git 三大主題，請在每個主題完成時進行 Commit。
1. 完成後，請發送 PR 至 `mid-term` 分支。
1. 也就是說，你的 PR 應該只會有三或四次的 Commit。

## Ruby 題目 (50 分)

1. (10 分) 請完成本題實作內容

```ruby
class Cat
  # 請完成實作
end

kitty = Cat.new("kitty")
puts kitty.name  # 在畫面上印出 kitty 字樣
```
Answer
```ruby
class Cat
  
  def initialize(name)
      @name = name
  end
  
  def name
      puts @name
  end
end

kitty = Cat.new("kitty")
puts kitty.name  # 在畫面上印出 kitty 字樣
```
2. (5 分) 假設有個 Hash：

```ruby
profile = {name: "kk", age: 18}
```

當執行這行程式：

```ruby
p profile["name"]
```
會得到什麼結果? 為什麼?

Answer
```ruby
會得到 nil，因為在Hash中它的Key是:name而非"name"
```

3. (5 分) 如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？

Answer
```ruby
 puts [*1..100].sample(5)
```

4. (10 分)

```ruby
class Bank
  def transfer(amount)
    # ...
  end
end

Bank.transfer(10)
```

上面這段程式碼執行後會發生什麼事？為什麼？如果有錯誤又該如何修正？

Answer
```ruby
找不到trankfer這個方法
```

5. (10 分) 請問以下方法：

```ruby
link_to "刪除", products_path(product), method: :delete, class: "btn btn-default"
```

`link_to` 方法共有幾個參數？為什麼？

Answer
```ruby
三個，用中跨號誇起來的是參數
{[link_to "刪除"], [products_path(product)], [method: :delete, class: "btn btn-default"]}
```

6. (10 分) 在 Ruby 裡面常會看到冒號的寫法，例如：

有的冒號靠右邊：

```ruby
class Store
  has_many :products
end
```

有的冒號靠左邊：

```ruby
link_to "檢視", books_path(book), class: "btn btn-default"
```

或是兩邊都有：

```ruby
user_profile = {name: "kk", age: 18, blood_type: :b_negative}
```

請問，這三種寫法分別代表什麼意思呢？

Answer
```ruby
冒號靠右邊的是代表著Symbol，Symbol有一點像String，但也不完全是Symbol，最大的差異就是當產生一個新的String需要花新的記憶體，Symbol不用。
冒號靠左邊的是代表著要套用的方法。
冒號兩邊都有的是怕使用到重覆的名稱而設計的。
```

## Rails 題目 (30 分)

1. (10 分) 請簡述 `bundle install` 指令的用途。

Answer
```ruby
是用來安裝套件的指令
```

2. (10 分) 請說明 `rails db:migrate` 這個指令的用途是什麼？

Answer
```ruby
更新資料庫，轉換成真實資料表
```

3. (10 分) 假設某個 Controller 的程式碼如下：

```ruby
class BooksController < ApplicationController
  def index
    @books = Book.all
  end

  def update
    @book = Book.find_by(id: params[:id])
    @book.update(price: 100)
    redirect_to books_path, notice: "資料更新成功"
  end
end
```

請問：
- 第 3 行的 `@books` 前面的那個 `@` 是什麼意思？如果把 `@` 拿掉會發生什麼事？

Answer
```ruby
View會找不到books。
```
- 第 7 行以及第 8 行的 `@book`，如果把 `@` 拿掉會發生什麼事？為什麼？

Answer
```ruby
會不知道要更新哪一本書。
```

## Git 題目 (20 分)

1. (10 分) 在你想像中的分支(branch)，是個什麼樣子的東西?

Answer
```ruby
我覺得有點像是書籤，就像是一本書有很多人看，每個人都用不同的書籤標記著自己看到的頁碼，突然有一天兩個人一起看這本書，他們也可以共用這個標籤
```

1. (5 分) 空的資料夾無法被加入 Git 版控，但如果就是想讓這個資料夾留下來，你會怎麼處理?

Answer
```ruby
新增一個空白檔案放入該資料夾
```

2. (5 分) 如果有些檔案，像是 `/config/database.yml` 之類比較機密的檔案，不想放在 Git 裡面，你會怎麼做？

Answer
```ruby
在專案目錄裡放一個 .gitignore 檔案，並且在裡面設定想要忽略的規則就行了
```

