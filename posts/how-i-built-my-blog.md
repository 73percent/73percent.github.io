---
title: Tôi đã xây dựng blog của mình như thế nào
published: true
date: 2019-02-05 00:00:00
tags: random
description: Khai blog đầu xuân
image: https://scontent.fhan3-2.fna.fbcdn.net/v/t1.0-9/19420455_633136263557074_7841937636162364169_n.jpg?_nc_cat=111&_nc_oc=AQmsLmnx3K9OnmCQjXUI_41QfiwkKMQ9mB4LJ3mT4fEB8GKCS6oZzezlXk8oo0A6Mn0OdxgkIHD6UrdiKqcWCsmV&_nc_ht=scontent.fhan3-2.fna&oh=64eaf45da97c67edbb28c23fd947d44e&oe=5CBE3C03
---
Vậy là năm 2018 âm lịch đã kết thúc rồi và mở ra một chương mới đó là năm 2019, tôi quyết định làm một cái
gì đó mới mẻ sau bao nhiêu năm ăn hại :think-cry:
  Thế là mấy hôm này mỗi hôm một ít lại hì hục đi built cái blog của riêng của mình dựa trên mã nguồn của ristretto-rs [^1] này lên Github. Bài viết này K. sẽ tranh thủ giới thiệu qua một chút về cái mã nguồn này dù mình chỉ đi customize lại rồi publish lên github :p.

## Nó hoạt động như thế nào 
Blog engine này được xây dựng dựa trên rust với cơ chế hoạt động khá đơn giản :
    Post.md  ----> Generator-rs  ----> Post.html ----> Github pages

Trong project Ristretto-rs, nhân vật chính, cũng là bộ chuyển đổi đó là folder generator-rs, source của folder này thì dài đến cả ngàn dòng, nhưng nhìn chung chức năng của nó là: Chuyển đổi tất cả các file Markdown ở trong thư mục /posts thành HTML.

Sau khi viết bài xong, chỉ cần chạy generator và thế là bạn đã có tất cả các file HTML cần thiết, chỉ việc copy nó lên một cái HTTP server nào đó là xong như mình là upload lên github pages.

### Cách build 
 Để build blog này thì đầu tiên các bạn vào folder generator-rs rồi gõ .
 ```
  cargo build
```
  Sau đó thì chỉ cần chở vài phút là nó build xong !
  Rồi sau đó copy generator-rs.exe trong generator-rs/target/debug ra folder mẹ 
  Cuối cùng các bạn chỉ cần chạy trong cmd :
```
generator-rs.exe posts
```
    
    
Vậy là xong , các post đã được generate thành các file html.

Lưu ý : Chỉ các file có mở đầu như hình dưới mới được generate, còn lại sẽ không được gen ra html :
  
  Và để customize blog thành cho riêng mình các bạn có thể edit lại các file html trong templates/

### Các chức năng của blog 
  Blog engine này được xây dựng với khá nhiều chức năng khá là hay như là emoji,comment,mathjax,...nên 
  cũng khá là thuận tiện cho các bạn trong việc viết blog của mình.
    Tuy nhiên không hiểu sao mình lại thấy cái comment bị lỗi nên đành phải thay thế bằng disqus :think-cry:

##  Conclusion
  Qua bài viết này mình đã hướng dẫn các bạn cách tự build blog của mình dựa trên blog engine ristretto-rs của thefullsnack (https://thefullsnack.com) #shamelesspr =)) .
   Mong rằng qua bài viết này các bạn có thể tạo được một blog riêng cho mình.
   Và đừng chần chừ gì nữa, hay subscribe ngay blog 73percent thôi nào :think-hopeful:

p/s: Lần đầu viết blog nên nếu có lỗi gì mấy thí chủ có thể comment ngay bên dưới

[^1]: blog engine của thefullsnack (https://github.com/huytd/ristretto-rs)

