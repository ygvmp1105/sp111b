> # 内容主要來源：
> [**Chatgpt**](https://chat.openai.com)<br>
# **使用 LLVM IR 語言，打印出一個帶有參數的字串**
```
; ModuleID = 'example'
source_filename = "example"

@formatString = private constant [15 x i8] c"Hello, %s!\n\00"

declare i32 @printf(i8*, ...)

define i32 @main(i32 %argc, i8** %argv) {
  entry:
    %str = getelementptr [15 x i8], [15 x i8]* @formatString, i32 0, i32 0
    %call = call i32 (i8*, ...) @printf(i8* %str, i8* %argv)
    ret i32 0
}
```
