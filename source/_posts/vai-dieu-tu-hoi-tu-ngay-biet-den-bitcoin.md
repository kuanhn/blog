---
title: Vài điều tự hỏi từ ngày biết đến Bitcoin
date: 2018-01-31 22:20:52
tags: 
    - blockchain
    - cryptocurrencies
category: Read
thumbnail: https://i.guim.co.uk/img/media/3c85b5db7cb852a0d45afa90049ed3b1b34c61a3/0_0_4000_2399/master/4000.jpg?w=300&q=55&auto=format&usm=12&fit=max&s=303b808f02d53abbeea1adb4ef587ed6
---
# Tản mạn
> Đứng dưới cái tiết trời 3ºC nhìn ngắm nguyệt thực toàn phần âu cũng làm con người ta dễ hoài niệm. Cái tâm trạng đó cũng dễ khiến người ta chỉ cần nhìn vào cái biểu đồ nến cũng gợi nhớ về bao chuyện từ hồi chân ướt chân ráo bước vào tìm hiểu Bitcoin.

Đấy là kiểu mấy ông nhà văn xàm xàm hay viết chứ thật ra cũng chỉ là mình muốn ghi chép lại mấy điều ngày xưa từng thắc mắc rồi tìm hiểu ra thôi. Về cơ bản thì cứ tìm hiểu lại thấy cái không hiểu nhưng dưới đây mình sẽ tổng hợp theo luồng suy nghĩ mình nghĩ là đơn giản nhất để sau này nếu có chia sẻ cho ai cũng dễ để biết bắt đầu từ đâu.

# Các vấn đề nối nhau xuất hiện
## Anh em có tậu con trâu điện về đào không?
Không phải là câu hỏi của mình nhưng đó chính là sự khởi đầu của tất cả các câu hỏi phía sau đây của mình. Sau hai ba câu chat mình mới biết là nó rủ mình đào coin vì đó đang là __trend__ lúc bấy giờ. Và sau cuộc nói chuyện đó mình chỉ biết công việc sẽ được mô tả như thế này:
> Build một __con trâu điện__ với 6 card đồ hoạ rồi chui vào một mỏ (__pools__) để làm công việc là "niêm phong" (__hash__) từng trang (__block__) của một cuốn sổ chứa nội dung là chính những giao dịch của một đồng coin rồi nhận phần thưởng trích ra từ phí của chính những giao dịch được ghi lại trong trang đó. 

Mặc dù tài ăn nói sử dụng tiếng Việt của mình cũng tạm nhưng mà nghĩ chắc mà đi giải thích được cái này cho người khác chắc cũng méo mồm. Tại sao nó không nói theo kiểu là mình dùng máy tính để làm công việc như một nhân viên ngân hàng, kiểm tra các giao dịch rồi nhận lương chính là phần trích ra từ phí phát sinh của những giao dịch đó cho nhanh?
Phải dùng cách mô tả mà bên trong đó đã xuất hiện bao nhiêu từ khoá để phải tra google cộng thêm đây có vẻ là một công nghệ mới nên quyết định tìm hiểu từ đầu cho đỡ bứt rứt.

## Hash là gì?
Thằng bạn mình nó dùng từ này và gọi nó là công việc. Cũng may là hồi học đại học đã được học rồi nên mới thấy quen quen nhưng lại không thể nhớ hết tính chất của nó nên tìm hiểu lại. Hoá ra đây lại chính là điều mà mọi tài liệu mình tìm hiểu về blockchain đều nói tới đầu tiên.

>Một ___Cryptographic Hash Functions___ hay còn gọi là hàm băm mật mã là một hàm số toán học mà qua đó một dữ liệu có độ dài bất kì sẽ biến thành một chuỗi có độ dài cố định. Khi tính giá trị của hàm __hash__ trên một chuỗi n-bit thì độ phức tạp của thuật toán là O(n).Ví dụ điển hình là SHA-256 một trong họ hàm __hash__ SHA-2 được thiết kế bởi NSA.

Khi tìm hiểu đến đây thì có vẻ đều là kiến thức đã được học nên mình không thấy có gì lạ lẫm cả, có chăng thì chỉ tra lại viết tắt của NSA (National Security Agency)

## Hàm hash có vai trò gì?
Nhớ lại lúc học về __hash__ thì được dạy nó có những tính chất như này:
- __Collision-resistance__ không tìm hai đầu vào $x$ và $y$ để cho $H(x) = H(y)$
- __Hiding one-way__ không thể tìm được đầu vào $x$ nếu biết được $y$ là kết quả của hàm $H(x)$
- __Puzzle-friendliness__ không thể tìm được giá trị $x$ để $H(k || x) = y$ trong thời gian ít hơn $2^n$ nếu cho trước giá trị $y$ và giá trị ngẫu nhiên $k$

Với mấy tính chất đó thì luôn đi kèm với mấy ví dụ ứng dụng như là _Message digests_ hoặc là _Commitment scheme_ hồi trên giảng đường. 
## Block là gì?
Khi xem lại hết mấy cái ví dụ về __hash__ vẫn chưa thấy sự liên quan ở đây nên mình chuyển vấn đề tìm hiểu sang __block__. Sau chỉ một lần tìm kiếm google cũng đã nhanh chóng có được câu trả lời như sau trên wikipedia
>Mọi dữ liệu trên mạng Internet đều rất dễ dàng bị sao chép, mỗi giao dịch Bitcoin cũng chỉ là một khối (__block__) thông tin. Bình thường, khi giao dịch trực tuyến, chúng ta sẽ cần đến một bên trung gian thứ ba mà chúng ta tin tưởng (ví dụ: công ty Paypal, công ty Ngân Lượng, Ngân hàng Vietcombank,...) với một cơ sở dữ liệu tập trung để xác minh giao dịch nhằm chống gian lận khi kẻ gian sử dụng lại khối thông tin này nhiều lần. Công nghệ blockchain đã giải quyết được bài toán này (double-spending) mà không cần tới bên trung gian thứ ba tin cậy. Blockchain là một cuốn sổ cái ghi lại tất cả các giao dịch. 

Không tìm thì thôi tìm thì lại thấy xuất hiện bao nhiêu là từ khoá mới để tìm hiểu. Thôi cứ từ từ bóc tách từng thằng một đọc xem sao.
## Blockchain là gì?
Khi tìm hiểu tới đây thì mọi đường dẫn đều nói đến Bitcoin thoạt đầu còn nghĩ blockchain là một khái niệm bên trong Bitcoin. Sau hai ba trang đều có cái mở đầu giống nhau _được phát minh bởi Satoshi Nakamoto dưới dạng phần mềm mã nguồn mở từ năm 2009_ thì mình quyết định tìm luôn cái phát minh đấy để đọc xem nó như thế nào. Và mình tìm thấy paper [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf) trong vài kết quả search. 
Tại đây mình lại nhìn thấy __hash__ nhưng được biểu diễn trỏ tới những __block__ liền kề một cách liên tiếp nhau trong một giao dịch (__Transactions__) Một cách dễ hình dung hơn thì ở một tài liệu khác mô hình đó được giới thiệu như sau:   

- Một con trỏ __hash__ có kèm theo giá trị hash của nội dung được trỏ tới.
![](https://learningspot.altervista.org/wp-content/uploads/2016/11/hash_pointer.png)

- Khi sử dụng con trỏ __hash__ thay cho con trỏ trong việc xây dựng cấu trúc dữ liệu linked list thì ta sẽ có cấu trúc mới được gọi là __blockchain__. 
![](https://learningspot.altervista.org/wp-content/uploads/2016/11/blockchain.png)

Ra là thế giờ thì đã biết cái định nghĩa của blockchain. Hoá ra ở mỗi block sẽ không chỉ trỏ tới block trước đó như ở linked list mà còn lưu giá trị hash của block được trỏ tới. Nếu dùng giá trị hash này ta có thể kiểm tra nội dung của khối được trỏ tới có toàn vẹn hay không. Và cứ thế nếu ta biết được giá trị hash ở cuối một chuỗi ta có thể xác định được nội dung của cả blockchain có bị thay đổi hay không.

## __Transactions__ đã được Satoshi đưa ra ứng dụng blockchain như thế nào?
Đây là hình ảnh được Satoshi mô tả trong paper:

![](https://i.stack.imgur.com/HUZQ2.jpg)

>Một đồng tiền điện tử được định nghĩa như một chuỗi của những giao dịch của những chữ kí điện tử. Một người chuyển coin cho một người khác bằng cách kí lên __hash__ của giao dịch trước đó và gắn khoá công khai của người nhận vào cuối của đồng coin. Người nhận có thể xác nhận chữ kí để chứng minh sự sở hữu của mình.

Đoạn trên mình dịch ra trong paper của Satoshi, ta thấy ở đây mô hình blockchain này có thêm khái niệm (__digital signature__). Nhắc đến nó thì lại cần đọc lại về ba thuật toán này.

- $(s_k,p_k) := generateKeys(keysize)$ Hàm tạo ra một cặp khoá công khai và một khoá bí mật. Tất nhiên như cái tên thì khoá bí mật $s_k$ thì chỉ mình biết, còn khoá công khai $p_k$ sẽ chia sẻ với với mọi gười.
- $sig := sign(s_k, message)$ Với khoá bí mật $s_k$ ta sẽ sử dụng để tạo ra chữ kí xác nhận cho _message_
- $sValid := verify(p_k, message, sig)$ Xác nhận chữ kí với khoá công khai $s_k$ giá trị trả về là true nếu sig đúng là chữ kí được tạo ra bởi khoá bí mật tương ứng $s_k$ và ngược lại sẽ là false.


Quay lại với mô hình của Satoshi, lúc này trong một giao dịch chuyển tiền giữa __Owner1__ và __Owner2__ thì:

- __Owner1__ sẽ kí lên mã __hash__ của khối giao dịch trước đó lần mà __Owner1__ là người nhận cùng với việc thêm vào địa chỉ người nhận TO: là khoá công khai của __Owner2__
- __Owner2__ lúc này sẽ dùng khoá công khai của __Owner1__,__hash__ và chữ kí để xác nhận vấn đề về tính đúng đúng đắn của giao dịch.

Thật ra mình đọc đến đây cũng phải mất rất lâu để thẩm (thấu) được cái hình đó. Không phải do sự khó hiểu về sự xác nhận của chữ kí điện tử mà là sự xác định sở hữu và giá trị của giao dịch làm mình mông lung. Lúc đó mình tự đặt những câu hỏi kiểu như
### Tại sao xác nhận được giao dịch trước thì lại tính là được sở hữu?
Để đơn giản nhất cứ nghĩ tới bước đầu tiên, bạn giao địch với cơ quan phát hành tiền tệ là Ngân hàng nhà nước X chẳng hạn. Nếu bạn xác nhận đúng đó là đồng tiền của cơ quan mà cả xã hội đang công nhận thì đó có thể được coi đang nắm giữ một giá trị trong xã hội. Tất nhiên những giao dịch sau đó những người khác đều xác nhận được giá trị đó không bị thay đổi thì giá trị của tài sản vẫn được đảm bảo.
### Nếu ví dụ có sự gian lận, người gửi giả mạo giá trị trong lần giao dịch trước để thay đổi quyền sở hữu thì sao? Lúc đó giao dịch không thành công và cả chuỗi sẽ dừng lại à?
Nếu đọc lại về blockchain và về con trỏ hash thì thấy rằng việc thay đổi nội dung giao dịch sẽ bị phát hiện bởi giá trị hash sẽ thay đổi. Khi này nếu như có sự giả mạo thì giao dịch sẽ thất bại, tất nhiên khi đó các giá trị tài sản trao đổi sẽ không mất. Còn về chuỗi nó vẫn sẽ tiếp diễn khi người sở hữu ở block cuối tiến hành một giao dịch.

## Ví dụ về một đồng tiền thuật toán (Cryptocurrency)?
Thấm xong được hai mục đầu của cái payper thì mình mới tìm được một ví dụ đơn nhất về đồng tiền thuật toán với tên gọi GoofyCoin.

![](https://steemitimages.com/0x0/http://learningspot.altervista.org/wp-content/uploads/2016/12/third_passage_of_coin.png)

Giả định Goofy có thể tạo ra đồng xu mới với một tuyên bố rằng ông ta làm ra một đồng xu mới với ID duy nhất. Và sau đó bất cứ ai sở hữu một đồng tiền có thể chuyển nó cho người khác bằng cách ký một tuyên bố nói rằng : "chuyển tiền xu này cho người X". Những người nhận hoàn toàn có thể xác minh tính hợp lệ của đồng xu bằng cách đơn giản theo chuỗi và xác minh tất cả các chữ ký trên đường đi.

## Double-spending là gì?
Nhưng đồng xu này là tồn tại một vấn đề mang tên __double-spending__, chính xác là cái vấn đề mà wiki nhắc đến hồi mới tìm hiểu. Mình cũng chưa biết là gì nên tìm định nghĩa luôn. 
>__Double-spending__ là hình thức gian lận hai giao dịch khác nhau để cùng chi tiêu một số dư.

Ban đầu khi đọc mình chưa hiểu được vì sao số dư lại chi tiêu được hai giao dịch. Sau đó mới ngộ ra trong cuộc sống cần phải có ngân hàng để là bên thứ ba giữa những cuộc giao dịch là như vậy, vì đó là bên đảm bảo điều gian lận kia không xảy ra được. Vậy xem ở xã hội không có ngân hàng của Goofy thì nó xảy ra như thế nào.


![](https://steemitimages.com/0x0/http://learningspot.altervista.org/wp-content/uploads/2016/12/goofy_coin_double_spending-960x451.png)

Nó sẽ diễn ra như sau:
- Goofy tạo một giao dịch với Alice
- Alice tạo một giao dịch với Bob
- Sau đó Alice tạo một giao dịch với Chuck cùng một giá trị

Tất nhiên sau đó cả Bob và Chuck đều có thực hiện những công việc xác nhận thành công. Lúc đó sẽ phát sinh việc một đồng coin lại có thể thực hiện cả hai giao dịch.

## Công nghệ blockchain đã giải quyết được bài toán double-spending như thế nào?
## Sau khi tìm hiểu đến đây rồi thì công việc áp dụng vào Bitcoin ra sao?

Sẽ còn chia sẻ ở bài sắp tới...