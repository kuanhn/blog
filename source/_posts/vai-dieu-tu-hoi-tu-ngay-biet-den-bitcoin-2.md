---
title: Vài điều tự hỏi từ ngày biết đến Bitcoin (P2)
date: 2018-02-02 22:36:13
tags: 
    - blockchain
    - cryptocurrencies
    - bitcoin
category: Read
thumbnail: /css/images/20180202/thumbnail.jpg
---
>## Liệu Bitcoin có thể là nơi mình kiếm được tiền từ đó?

Lần này mình sẽ mở đầu bằng câu hỏi mà hiện tại khi viết bài viết này mình vẫn chưa thể tự trả lời được. Trước những biến động gần đây thì có thể thấy những người 3 tháng trước vỗ ngực mình đã trở thành triệu phú đô la thì giờ đây lại trở về vạch xuất phát nhưng cũng không thể biết được 3 tháng sau họ sẽ như thế nào. Thôi thay vì bận tâm vào những điều không thể đoán trước được thì mình lại dành thời gian để tìm hiểu những điều mà người ta đã biết từ trước vậy. Nếu vô tình bạn cũng có hứng thú muốn tìm hiểu thì có thể tham khảo bài viết trước của mình ở [đây](../vai-dieu-tu-hoi-tu-ngay-biet-den-bitcoin-1/).

## Bitcoin là gì?
Về cơ bản thì __bitcoin__ cũng giống như ScroogeCoin nghĩa là cũng được xây dựng trên công nghệ blockchain và các đặc tính về một giao dịch cũng như vậy. Nhưng điều khác ở đây là "xã hội" này không tồn tại một cá thể duy nhất để đảm bảo tính ổn định của nó. Một mạng lưới các nút ngang hàng (peer-to-peer) sẽ đảm nhận điều đó. Bitcoin toàn cầu điều phối và ổn định các giao dịch bằng thuật toán. Để trả lời câu hỏi _**Bitcoin** là gì?_ thì quả thật nếu chỉ đọc những dòng định nghĩa trên [Wikipedia](https://vi.wikipedia.org/wiki/Bitcoin) thì thật sự không thỏa mãn lắm.
>Bitcoin (ký hiệu: BTC, XBT) là một loại tiền mã hóa, được phát minh bởi Satoshi Nakamoto dưới dạng phần mềm mã nguồn mở từ năm 2009. Bitcoin có thể được trao đổi trực tiếp bằng thiết bị kết nối Internet mà không cần thông qua một tổ chức tài chính trung gian nào.

Không tồn tại nhà điều hành trung ương thì thì các thuật toán và các nút sẽ vận hành mạng lưới này như thế nào? Đó là câu hỏi tiếp theo xuất hiện khi mình mình muốn tự tìm hiểu để có chút tự tin khi nói với ai đó về __bitcoin__. Có thể chia nhỏ ra để trả lời các câu hỏi như sau:
1. Ai duy trì các giao dịch?
2. Ai có thẩm quyền quyết định giao dịch nào hợp lệ?
3. Ai tạo ra bitcoins mới?
4. Ai thay đổi cách thay đổi các quy tắc của hệ thống?
5. Làm thế nào để bitcoins có được giá trị trao đổi?

# Một block của bitcoin sẽ như thế nào?
Như đã nói __bitcoin__ được xây dựng dựa trên công nghệ blockchain nên thôi cứ bắt đầu từ đơn vị nhỏ nhất là một block xem nó như thế nào. Dưới đây là hình ảnh mô tả blockchain của __bitcoin__.

![Bitcoin-blockchain](/css/images/20180202/bitcoin-block-chain.jpeg)

Ở đó chuỗi chính (màu vàng) bao gồm chuỗi block dài nhất tính từ block khởi đầu (genesis). Block màu đen không được chấp nhận do không đạt sự đồng thuận của mạng lưới.

Còn về chi tiết một block sẽ có những phần như sau:

![Bitcoin’s Block Structure](/css/images/20180202/bitcoin-block-structure.jpeg)

- Magic number (4 bytes): Đây là một số nhận diện cho mạng Blockchain do đó có giá trị không đổi là 0xD9B4BEF9. Nó chỉ ra điểm _Khởi đầu của block_ và _Dữ liệu từ mạng lưới sản xuất_.
- Block size (4 bytes): Cho biết kích thước của block là bao nhiêu. Kể từ khi bắt đầu cho đến ngày hôm nay mỗi block được cố định tối đa 1 MB.
- Version (4 bytes): Mỗi nút chạy giao thức Bitcoin phải thực hiện cùng một phiên bản và đây là trường xác định phiên bản đó.
- Previous block hash (32 bytes): Kết quả hash của header trong block trước đó. Nó được tính bằng cách dùng mã hóa SHA-256 tất cả các trường của header như version, nonce v..vv
- Merkle Root (32 bytes), Timestamp (4 bytes), Difficulty Target (4 bytes), Nonce (4 bytes): Những giá trị này định nghĩa thì mất thời gian nên sẽ nói ở những mục phía dưới.

Tất cả các trường vừa rồi sẽ quy định header của một block. Còn lại
- Transaction Counter (1–9 bytes) : ghi lại số lượng các giao dịch được ghi trong block
- Transaction List (Tối đa 1MB): Danh sách các giao dịch.

Đây là block [đầu tiên](https://blockchain.info/block/000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f) của Bitcoin và block [gần nhất](https://blockchain.info/en/block/0000000000000000003f0bb48eecd4e38c4d07ce88f83ce21dc7a7c94474be2b) của Bitcoin trong thời điểm mình viết bài này.

## Merkle Root là gì?
![Merkle Root](/css/images/20180202/merkle-root.PNG)
Như đã nói thì mỗi block có một danh sách tóm tắt của tất cả các giao dịch. Một khi block là một phần của blockchain thì nội dung của nó khó có thể thay đổi hoặc có thể nói là không thể. Các giao dịch được liệt kê như cây merkle (cây băm nhị phân).

Mỗi lá sẽ là một giao dịch và sẽ được thực hiện và xác nhận như mình đã nói ở phần trước trong mục Transactions. Sau đó mỗi giao dịch này sẽ được hash lại bằng mã hóa SHA256 hai lần nghĩa là Hash [Tx3] = SHA256 (SHA256 (Tx3)).
Tương tự như vậy để xây dựng một nút cha Hash(23) 32 byte Hash [Tx2] và 32 byte Hash [Tx3] được ghép nối như là một chuỗi hash 64 byte và sau đó SHA256 được áp dụng hai lần để cho ra một Hash 32 byte. Gốc cây là nút trên là hash của tất cả.
Định nghĩa là như vậy nhưng mục đích của nó là gì thì phải xét đến việc xác nhận giao dịch. Thông qua kết quả hash của gốc rất dễ dàng để xác định liệu một giao dịch cụ thể có nằm trong block hay không.

## Timestamp ư? Tại sao lại có thời gian ở đây?
Tiếp theo là một khái niệm nữa trong cấu trúc của một block. Lặp lại về vấn đề double-spend ở bài trước, ở mạng lưới __bitcoin__ thì vấn đề này cũng phải được giải quyết. Nghĩa là cần một giải pháp làm sao để người nhận biết rằng người bán đã không "ký" lên một giao dịch nào trước đó. Và ý tưởng ở đây được đưa ra là giao dịch sớm nhất là giao dịch được chấp nhận không cần quan tâm sau có trường hợp double-spend xảy ra hay không. Và cách duy nhất để xác minh điều đó là tất cả các giao dịch cần được công khai. Những nút trong mạng lưới sẽ biểu quyết (vote) để công nhận một lịch sử giao dịch duy nhất. Một người nhận hợp pháp khi anh ta có thể chứng minh rằng giao dịch nơi mình nhận được là giao dịch sớm nhất trong chuỗi lịch sử giao dịch được cộng đồng công nhận này. Và khi đó sẽ giải quyết được vấn đề nếu có sự gian lận xảy ra ở đây. Người nhận thứ hai có thể dựa vào danh sách tất cả các giao dịch để phát hiện gian lận. Trong trường hợp người gửi không chứng minh được sự sở hữu của tài sản do đó không phải là giao dịch đầu tiên với tài sản này thì cũng chẳng thế thực hiện được giao dịch nào tiếp theo cả. 

__Timestamp__ được đưa ra ở đây là để thực hiện việc xác minh thời gian đó. Tất nhiên giá trị này cũng được hash và giá trị tiếp theo sẽ bao giá trị thời gian của những block trước đó như đặc tính của blockchain khi đó nó sẽ không thể bị giả mạo.

## Network ở đây là gì?
Tất nhiên ở đây không chỉ nói network là mạng lưới, từ khi tìm hiểu mình cũng chỉ biết dưới tên mạng lưới ngang hàng (peer-to-peer network) là tính chất của  mạng lưới __bitcoin__. Thế nhưng mạng lưới này hoạt động như thế nào mà mọi khái niệm vừa rồi đều thấy nhắc đến.
Mạng lưới của __bitcoin__ được Satoshi giới thiệu sẽ vận hành theo các bước sau.

1. Các giao dịch mới được công khai tới tất cả các nút.
2. Mỗi nút thu thập các giao dịch mới vào một block.
3. Mỗi nút thực hiện việc tìm kiếm một giá trị chứng minh proof-of-work của block đó.
4. Khi một nút tìm thấy giá trị chứng minh trên nó công khai block cho tất cả các nút.
5. Các nút khác chấp nhận block chỉ khi tất cả các giao dịch trong đó là hợp lệ và chưa được chi tiêu.
6. Các nút thể hiện sự chấp nhận của block này bằng cách tạo ra block tiếp theo trong chuỗi và gắn hash của block được chấp nhận trước đó.

Đến đây thì có thể hiểu ra được phần nào câu trả lời cho những câu hỏi như 
>1. Ai duy trì các giao dịch?
>2. Ai có thẩm quyền quyết định giao dịch nào hợp lệ?
>4. Ai thay đổi cách thay đổi các quy tắc của hệ thống?

Tất cả đều do các nút trong mạng lưới quyết định, mỗi một nút sẽ có một quyền vote các hoạt động của mạng lưới. Vậy việc vote này sẽ thực hiện như thế nào, chẳng nhẽ có một cái "hòm" thống kê rồi mỗi nút sẽ "bỏ phiếu" vào đó. Nếu như vậy thì thủ công quá, vote ở đây có thể dễ hình dung qua một ví dụ về trường hợp có hai nút công khai một block cùng một lúc. Tất nhiên lúc này sẽ có khả năng tạo ra hai nhánh ứng với nút cuối là hai block này, các nút sẽ lại bắt đầu thực hiện công việc tìm kiếm trên block đầu tiên mà nút đó nhận được, hoặc cũng có thể là block sau. Chỉ đến khi công việc ở một trong hai block được hoàn thành trước và nhánh chứa block đó trở nên dài hơn khi đó nhánh còn lại đương nhiên bị hủy bỏ. Một cách thông thường thì những nhánh có nhiều nút làm việc hơn tất nhiên sẽ đưa ra được kết quả nhanh hơn rồi. Đó chính là kết quả của việc vote, mỗi nút sẽ quyết định chọn nhánh và block của nhánh để làm việc và lựa chọn của đa số sẽ được quyết định.

## Proof-of-work ở đây là gì?
Tiếp theo còn một câu hỏi bị bỏ lửng ở giữa _3. Ai tạo ra bitcoins mới?_ hay _5. Làm thế nào để bitcoins có được giá trị trao đổi?_ Mấu chốt để trả lời câu hỏi này sẽ nằm ở bước 3 và 4 trong sự hoạt động của network và đây cũng chính từ đây có thể miêu tả về công việc đào coin mà lần đầu mình đã nhắc đến.

Proof-of-work hay bằng chứng công việc là một cách để thể hiện sự khó khăn để kiếm ra được __bitcoin__ bởi vì để thực hiện công việc này cần tốn thời gian và tiền bạc. Để có thể được cả mạng lưới chấp nhận, block mới cần phải chứa giá trị Proof-of-work. Proof-of-work yêu cầu mỗi nút tìm kiếm một số nonce, mà khi nội dung của block được hash cùng nonce, kết quả tạo ra một số nhỏ hơn số target của mạng lưới (số target càng nhỏ thì độ khó càng cao). Nói cách khác: Proof-of-work rất dễ cho các máy tính xác nhận, nhưng cực kỳ mất nhiều thời gian để có thể tạo ra. Các nút phải thử rất nhiều giá trị nonce khác nhau trước khi đạt được độ khó mà mạng lưới yêu cầu. Tại thời điểm khi viết bài viết này dựa theo số tiền điện để vận hành các nút thì chi phí cho việc kiếm được một __bitcoin__ vào khoảng 5040$.

Tại sao lại có sự yêu cầu khó khăn này? Đó là bởi vì khi mỗi block được đưa nối vào chuỗi thì nút đã thực hiện công việc trên block đó sẽ nhận được 12,5 __bitcoin__ và toàn bộ phí giao dịch được viết trong block này. Máy tính có hiện đại thì việc thực hiện hàng triệu phép toán mỗi giây không phải là điều gì đó khó khăn nữa. Sự khó khăn được đưa ra để đảm bảo sự giãn cách khoảng 10 phút mới có một block được công khai. Cũng như những quy định cứ 2016 block được công khai thì độ khó sẽ lại thay đổi, 210.000 block được thêm vào thì phần thưởng sẽ giảm một nửa. Chính dựa vào sự khó khăn rồi khan hiếm dần theo thời gian sẽ tạo nên giá trị trao đổi cho __bitcoin__. Tất nhiên độ khó cũng sẽ có thể tăng hoặc giảm tùy theo vote của cả hệ thống. Để "thích nghi" được với sự khó khăn này thì các nút riêng lẻ sẽ tập hợp lại với nhau để cùng làm công việc trên mỗi một block. Sự tập hợp này được gọi thành các bể đào (pools). Điều này sẽ giúp gia tăng khả năng có được kiếm được bitcoin khi mà sức mạng của các máy tính riêng lẻ được tập hợp lại. Tất nhiên sau đó thành quả sẽ được chia sẻ theo công đóng góp mà chủ yếu dựa vào số phép thử hash mà mỗi nút thành viên đã thực hiện.

## Difficulty và Target?
Đến đây thì cũng đã tìm hiểu được hầu hết những thứ cơ bản về __bitcoin__ rồi nhưng tò thêm về hai thuật ngữ quyết định độ khó vừa được nhắc tới Difficulty và Target nên lại voọc wiki thêm một chút nữa.
__Target__ là một số 256-bit mà tất cả các nút công nhận. Hash SHA-256 của block header phải nhỏ hơn hoặc bằng __target__ hiện tại của block để được chấp nhận bởi mạng. __Target__ càng thấp, càng khó tạo block.
__Difficulty__ dùng để đo mức độ khó khăn được tìm được một giá trị hash mà nhỏ hơn __target__ nhất định. Toàn bộ mạng lưới sẽ có chung một giá trị __difficulty__ tuy nhiên khi tham gia vào các bể đào thì độ khó này cũng có thể bị thay đổi do có thêm việc tính toán chia thành quả sau này.

## Kiếm khó khăn như vậy nhưng để mất bitcoin thì sao?

Vì có những tính chất của tiền tệ: Đáng giá, lưu thông, dự trữ, thanh toán nên __bitcoin__ đang trở thành tài sản của thế hệ mới với nhiều đặc điểm vượt trội như:
- Không cần trung gian thanh toán nên giảm thiểu chi phí.
- Không thể tự làm ra hoặc làm giả. Hơn nưa không mất chi phí giám định như với các tài sản như vàng.
- Dễ dàng chia nhỏ và thanh toán.
- Bảo vệ môi trường.

Nếu như vậy thì có vẻ __bitcoin__ là loại tiền tệ rất đáng để lưu trữ. Vậy lưu trữ __bitcoin__ như thế nào?
Mỗi tài khoản Bitcoin được biểu diễn dưới dạng một ví Bitcoin. Mỗi ví Bitcoin bao gồm địa chỉ Bitcoin công khai (hash của public key) và khóa bí mật (private key). Một địa chỉ có 160 bit dữ liệu, vì vậy có thể tạo ra tổng cộng $2^{160}$ địa chỉ Bitcoin - tương đương $10^{48}$ địa chỉ. Ngoài ra địa chỉ còn bao gồm 4 byte checksum nên xác suất mạng lưới chấp nhận địa chỉ Bitcoin gõ sai cực kỳ thấp. Bất kỳ ai cũng có thể gửi Bitcoin đến một chiếc ví bằng địa chỉ công khai, còn khoá bí mật phải được nhập khi chủ ví muốn gửi Bitcoin đi. Vì vậy, việc sở hữu Bitcoin được định nghĩa là sự nắm giữ khoá bí mật của một địa chỉ Bitcoin.

Giao dịch mọi thứ đều dễ dàng như vậy nhưng nếu đánh mất khóa bí mật cũng đồng nghĩa với việc __bitcoin__ trong đó sẽ mất hay có thể hiểu khó mà có thể chi tiêu được nữa. Tại sao mình lại dùng từ "khó" bởi vì việc lấy lại khóa bí mật sau khi sinh ra là không có nhưng có thể dùng phương pháp vét cạn để tìm lại. :D

## Vấn đề của mạng lưới bitcoin?
Trong khi tất cả các mọi thứ về blockchain còn nằm trong ý tưởng thì Bitcoin đã trở thành tiên phong của công nghệ này khi được thử nghiệm theo thời gian và được hàng triệu người sử dụng. Tuy vậy mạng lưới __bitcoin__ vẫn không phải là hoàn hảo và nó vẫn còn những vấn đề tiềm ẩn.__TẤN CÔNG 51%__ là cách mà người ta nhận định về vấn đề của mạng lưới __bitcoin__. Khi một nút hay một pools có khả năng kiểm soát 51% sức mạnh máy tính của cả hệ thống. Lúc này việc tạo ra những gian lận, hoặc hủy bỏ những block hợp lệ là điều có thể xảy ra. Mặc dù hiện nay thì điều này vẫn chỉ nằm trong lý thuyết nhưng đó cũng là lý do để những công nghệ mới hơn được nghiên cứu cải tiến và đưa ra thực hiện.

## _Ethereum là câu trả lời cho việc đó._