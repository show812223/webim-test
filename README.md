# WeBIM 面試考題

- 請使用typescript與vue conposition api實作以下題目
- 專案已引用vueitfy, 可使用vueitfy元件實作畫面

## 題目 : 設計一個動物系統（Animal System）

請設計一個 **`Animal`** 抽象類別，並實作以下功能：

1. `Animal` **為抽象類別**，應包含：
    - **`name` 屬性**（受保護，不能直接從外部存取）。
    - **`makeSound()` 抽象方法**，讓子類別去實作不同的叫聲。
2. **請建立兩個子類別** `Dog` 和 `Cat`，並繼承 `Animal`：
    - `Dog` 的 `makeSound()` 回傳 `"汪汪"`
    - `Cat` 的 `makeSound()` 回傳 `"喵喵"`
3. `Animal` 應提供一個 `getName()` 方法來取得 `name`，但 `name` 屬性不能直接被外部存取。
4. 請建立一個函式 `printAnimalSound(animal: Animal)`，該函式應能接受 `Dog` 或 `Cat`，並印出其 `makeSound()` 的結果。
5. 請建立一個頁面`Zoo`, 並在頁面上顯示兩個按鈕，分別是`Dog`和`Cat`，點擊按鈕後，會在頁面上顯示對應的叫聲。

