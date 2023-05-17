<p align="center">
 <h1 align="center">Cấu trúc điều khiển và vòng lặp trong Python</h1>
</p>

# Giới thiệu
- Cấu trúc điều kiện và vòng lặp là những lệnh rất phổ biến khi lập trình không chỉ trong ngôn ngữ Python mà còn trong tất cả các ngôn ngữ lập trình.
- Khi ta muốn thực hiện một khối lệnh nào đó trong Python chỉ khi một điều kiện nào đó được thỏa mãn, cấu trúc điều kiện là thứ mà ta cần dùng trong trường hợp này. Còn khi ta muốn thực hiện một khối lệnh nào đó nhiều lần, hoặc với từng phần tử trong một đối tượng mảng, ta sẽ sử dụng tới cấu trúc vòng lặp.

# Cấu trúc điều khiển

## Câu lệnh if
- Câu lệnh if được sử dụng để kiểm tra một điều kiện: nếu điều kiện là đúng sẽ chạy một khối các câu lệnh (được gọi là if-block).

```
if BOOLEAN EXPRESSION:
    STATEMENTS
```

![image](https://github.com/thangdtph27626/python-basic.github.io/assets/109157942/954bdf25-e791-43d3-a6c8-07dded914434)


> lưu ý:
- Dấu hai chấm ( :) là quan trọng và bắt buộc. Nó tách phần đầu của câu lệnh ghép khỏi phần thân .
- Dòng sau dấu hai chấm phải được thụt vào. Tiêu chuẩn trong Python là sử dụng bốn khoảng trắng để thụt lề.
- Tất cả các dòng được thụt vào cùng một lượng sau dấu hai chấm sẽ được thực thi bất cứ khi nào BOOLEAN_EXPRESSION là đúng.

ví dụ:

```
food = 0

if food == 0:
    print('true')
```

## Câu lệnh if else
- Khối else sẽ được thực thi nếu điều kiện trong if là sai

```
if BOOLEAN EXPRESSION:
    STATEMENTS_1        # thực hiện nếu điều kiện đánh giá là True
else:
    STATEMENTS_2        # thực hiện nếu điều kiện đánh giá là  False
```

![image](https://github.com/thangdtph27626/python-basic.github.io/assets/109157942/f70bff43-1d14-47f2-a7ff-46082f83cb78)

ví dụ:

```
food = 0
if food == 0:
    print('true')
else:
    print("false")
```

### Chuỗi điều kiện

- Khi ta phải kiểm tra thêm một điều kiện nữa nếu trong if là sai ta có thể sử dụng elif

```
if x < y:
    STATEMENTS_A
elif x > y:
    STATEMENTS_B
else:
    STATEMENTS_C
```

![image](https://github.com/thangdtph27626/python-basic.github.io/assets/109157942/bc3b899d-7c90-46a4-bbbe-a4de2d31257b)

ví dụ:

```
if choice == 'a':
    print("You chose 'a'.")
elif choice == 'b':
    print("You chose 'b'.")
elif choice == 'c':
    print("You chose 'c'.")
else:
    print("Invalid choice.")
```

### Điều kiện lồng nhau
- Một điều kiện cũng có thể được lồng trong một điều kiện khác. (Đây lại là chủ đề tương tự về khả năng kết hợp!) Chúng ta có thể viết ví dụ trước như sa

```
if x < y:
    STATEMENTS_A
else:
    if x > y:
        STATEMENTS_B
    else:
        STATEMENTS_C
```

![image](https://github.com/thangdtph27626/python-basic.github.io/assets/109157942/dca18ee2-6772-4beb-b09a-4c5493386365)

ví dụ:

```
if numberInput == 1:
    print("numberInput is one")
else:
    if numberInput == 2:
        print("numberInput is two")
    else:
        print("numberInput is not one or two")
```

## Switch 

- Có một điều đặc biệt hơn các ngôn ngữ khác là Python không có Switch case. Thay vào đó chúng ta có thể sử dụng if...elif....else để thay thế cấu trúc switch case (hơi bất tiện nhỉ, thế nếu mà có 8 - 10 case thì cứ if else thế này chắc khó đọc quá?)
- Sử dụng một chức năng và eliftừ khóa là một trong số đó và bạn có thể làm theo cách này:

```
def switch(lang):
    if lang == "JavaScript":
        return "You can become a web developer."
    elif lang == "PHP":
        return "You can become a backend developer."
    elif lang == "Python":
        return "You can become a Data Scientist"
    elif lang == "Solidity":
        return "You can become a Blockchain developer."
    elif lang == "Java":
        return "You can become a mobile app developer"

print(switch("JavaScript"))   
print(switch("PHP"))   
print(switch("Java"))  
```

> matchvà casetrong Python 3.10
 Để viết câu lệnh switch với tính năng khớp mẫu cấu trúc, bạn có thể sử dụng cú pháp bên dưới:

```
match term:
    case pattern-1:
         action-1
    case pattern-2:
         action-2
    case pattern-3:
         action-3
    case _:
        action-default
```

# Cấu trúc vòng lặp

- Trong lập trình, vòng lặp là một trong những cấu trúc thường gặp nhất bên cạnh cấu trúc điều kiện đã đề cập ở trên. Người ta sử dụng vòng lặp để thực hiện lặp lại một khối lệnh nào đó.
- Các cấu trúc vòng lặp trong Python gồm 2 loại: for, while

## Vòng lặp với số lần xác định(for)

```
for [biến chạy] in range(start:stop):
     [khối lệnh]
    
for [biến chạy] in [iterable]:
     [khối lệnh]
```

ví dụ:

```
words = ['cat', 'dog', 'bird'];
for w in words:
    print(w)

output:
cat
dog
bird
```

- range(): giúp chúng ta có thể tạo ra một list một cách nhanh chóng. Với cú pháp:
- Với cú pháp này tạo ra 1 list bắt đầu từ 0 liên tục và kết thúc khi có đủ elementNumbers:
 - Hàm range() có 3 tham số:
  + start: số nguyên bắt đầu, chuỗi sẽ bắt đầu với tham số này. Giá trị mặc định là 0.
  + stop: số nguyên kết thúc, chuỗi sẽ kết thúc với tham số này.
  + step: số nguyên xác định khoảng cách giữa các số bên trong chuỗi. Giá trị mặc định là 1.
 ví dụ:
 
 ```
 for number in range(5):
    print(number)
 
 output:
0
1
2
3
4
 ```
 
 ## Vòng lặp với số lần không xác định (while)
 -vòng lặp while trong python tương tự trong các ngôn ngữ khác, lặp khi thỏa mãn điều kiện cho trước. Cú pháp:
 
 ```
 while [điều kiện]:
     [khối lệnh]
 ```
 
 - break và continue:break cho phép thoát khỏi vòng lặp, còn continue cho phép bỏ qua lượt chạy hiện tại của vòng lặp và chạy tiếp.

ví dụ:

```
i = 0
while (i <= 10):
	print(i)
	if i == 5:
		break
	i += 1

for i in ‘i am a robot’:
	if i == ‘ ’:
		continue
	print(i, end=’’)
```

#  Kết luận

Với bài viết trên đây, hy vọng các bạn sẽ có thể làm quen được với cấu trúc điều kiện và vòng lặp trong ngôn ngữ Python - hai cấu trúc được sử dụng thường xuyên không chỉ trong Python mà còn ở rất nhiều các ngôn ngữ lập trình khác. Các bạn có thể tự suy nghĩ để áp dụng cấu trúc điều kiện và vòng lặp này để viết một số chương trình đơn giản
