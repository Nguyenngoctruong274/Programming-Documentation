## Repository Pattern
 là một mẫu thiết kế phần mềm trong lập trình phần mềm. Nó được sử dụng để tạo ra một lớp trung gian (repository) để tương tác với các đối tượng dữ liệu của ứng dụng, giúp tách biệt lớp xử lý dữ liệu (data access layer) khỏi lớp logic kinh doanh (business logic layer). Mục tiêu chính của Repository Pattern là cung cấp một giao diện duy nhất để thao tác với dữ liệu, giảm sự phụ thuộc trực tiếp của lớp logic kinh doanh vào các cơ sở dữ liệu hoặc các nguồn dữ liệu khác.
 [Microservicec]([http://https://vi.wikipedia.org/wiki/Markdown](https://miro.medium.com/v2/resize:fit:1400/1*XQS6j3Bdp1Fcl1EijAoUyQ.png))

 # HTTP
Một máy chủ HTTP cơ bản có một số công việc chính cần đảm nhiệm
1. Xử lý các yêu cầu động: Xử lý các yêu cầu đến từ người dùng duyệt trang web, đăng nhập vào tài khoản của họ hoặc đăng hình ảnh. 
2. Cung cấp nội dung tĩnh: Cung cấp JavaScript, CSS và hình ảnh cho trình duyệt để tạo trải nghiệm động cho người dùng.
3. Chấp nhận kết nối: Máy chủ HTTP phải lắng nghe trên một cổng cụ thể để có thể chấp nhận kết nối từ internet.
Gói net/http của Go cung cấp nhiều chức năng cho giao thức HTTP nhưng một điều nó không làm tốt lắm là việc định tuyến yêu cầu phức tạp như phân đoạn url yêu cầu thành các tham số đơn lẻ. Vì thế sử dụng gói **gorilla/mux** để tạo các tuyến đường có tham số được đặt tên.
`https://gowebexamples.com/routes-using-gorilla-mux/`

## Middleware 
Middleware được sử dụng để xử lý các yêu cầu HTTP trước khi chúng được chuyển đến các xử lý chính (handler). Middleware thường được sử dụng để thực hiện các công việc như:
* Xác thực (Authentication): Middleware có thể kiểm tra xem yêu cầu được gửi có đúng là từ một người dùng được xác thực hay không.
* Xác thực quyền truy cập (Authorization): Middleware có thể kiểm tra quyền truy cập của người dùng vào các tài nguyên hoặc hành động cụ thể.
* Ghi nhật ký (Logging): Middleware có thể ghi lại các yêu cầu đến hệ thống và các phản hồi được trả về từ hệ thống
* Gán các giá trị (Context): Middleware có thể thêm hoặc sửa đổi thông tin trong một ngữ cảnh (context) của yêu cầu, cho phép chuyển tiếp dữ liệu giữa các middleware hoặc giữa middleware và xử lý chính.
* Xử lý lỗi (Error handling): Middleware có thể bắt và xử lý các lỗi từ các xử lý chính, cung cấp một cơ chế chung để xử lý các lỗi trong ứng dụng.


## Seessions
Session là một cách để lưu trữ và duy trì trạng thái của một phiên làm việc giữa các yêu cầu HTTP của người dùng. Session thường được sử dụng để lưu trữ thông tin phiên như thông tin đăng nhập của người dùng, giỏ hàng mua sắm, cài đặt ngôn ngữ hoặc bất kỳ dữ liệu nào khác cần được duy trì trong suốt quá trình tương tác với ứng dụng web.

## WebSocket 
WebSocket là một công nghệ cho phép thiết lập một kết nối liên tục và hai chiều giữa trình duyệt web và máy chủ. Khác với HTTP, nơi mỗi yêu cầu đều tạo ra một kết nối mới, WebSocket cho phép truyền dữ liệu theo thời gian thực giữa hai bên mà không cần thiết lập lại kết nối.

Tại sao chúng ta cần sử dụng WebSockets thay vì chỉ sử dụng HTTP truyền thống?

Trả lời: WebSockets được sử dụng khi cần truyền dữ liệu theo thời gian thực hoặc khi cần thiết lập kết nối hai chiều giữa trình duyệt và máy chủ. Điều này rất hữu ích cho các ứng dụng như trò chơi trực tuyến, ứng dụng trò chuyện và cập nhật dữ liệu thời tiết, nơi cần cập nhật dữ liệu đồng bộ và liên tục.



## HTTPS 
HTTPS (Hypertext Transfer Protocol Secure) là một phiên bản bảo mật của giao thức HTTP, được sử dụng để truyền tải dữ liệu an toàn và bảo mật trên Internet. HTTPS sử dụng SSL (Secure Sockets Layer) hoặc TLS (Transport Layer Security) để mã hóa dữ liệu trước khi truyền đi, ngăn chặn bất kỳ ai có thể đọc hoặc hiệu chỉnh dữ liệu trong quá trình truyền tải.
Khi sử dụng HTTPS, dữ liệu được mã hóa trước khi được gửi đi và được giải mã khi đến nơi. Điều này giúp đảm bảo rằng thông tin như tên người dùng, mật khẩu, thông tin cá nhân và tài liệu nhạy cảm khác không bị lộ khi được truyền qua Internet.

## Goroutines 
Goroutines là một tính năng quan trọng trong ngôn ngữ lập trình Go, cho phép thực hiện các công việc đồng thời một cách hiệu quả. Goroutines giúp tận dụng được các tài nguyên hệ thống bằng cách thực thi nhiều công việc đồng thời trên một luồng duy nhất (thread) mà không cần phải tạo ra các luồng mới. Điều này giúp giảm tải cho hệ thống và tăng hiệu suất.

## Prepared Statements
Prepared statements là một cơ chế cho phép bạn chuẩn bị và biên dịch các truy vấn SQL trước, sau đó sử dụng lại chúng với các tham số khác nhau mà không cần phải biên dịch lại từng lần thực thi. Điều này giúp cải thiện hiệu suất và an toàn cho ứng dụng của bạn, đặc biệt là khi xử lý các truy vấn SQL có tham số từ dữ liệu người dùng.

* Chuẩn bị truy vấn:
Bạn sử dụng hàm db.Prepare() hoặc stmt.Prepare() để chuẩn bị một truy vấn SQL. Trong quá trình này, truy vấn SQL sẽ được gửi đến cơ sở dữ liệu để biên dịch, nhưng chưa được thực thi.

* Thực thi truy vấn với các tham số khác nhau:
Sau khi truy vấn được chuẩn bị, bạn có thể sử dụng phương thức stmt.Exec(), stmt.Query(), stmt.QueryRow() hoặc rows.Scan() để thực thi truy vấn với các tham số khác nhau. Các tham số này sẽ được thay thế vào các vị trí thích hợp trong truy vấn SQL.
### ****Lợi Ích****
- An toàn từ tấn công SQL Injection: Vì dữ liệu được truyền dưới dạng tham số, nên không có khả năng cho kẻ tấn công chèn các câu lệnh SQL độc hại vào dữ liệu người dùng.

- Tăng hiệu suất: Cơ chế prepared statements cho phép cơ sở dữ liệu biên dịch truy vấn chỉ một lần, sau đó có thể được sử dụng lại với các tham số khác nhau. Điều này giúp giảm thời gian và tài nguyên cần thiết cho việc thực thi truy vấn.

## SQL injection
SQL injection là một kỹ thuật tấn công phổ biến trong lĩnh vực bảo mật web, mà kẻ tấn công sử dụng để chèn các câu lệnh SQL độc hại vào các trường dữ liệu đầu vào của ứng dụng web. Khi ứng dụng không kiểm tra và xử lý đầu vào từ người dùng một cách an toàn, kẻ tấn công có thể thực hiện các câu lệnh SQL không mong muốn hoặc gian lận với dữ liệu trong cơ sở dữ liệu. Các hậu quả của cuộc tấn công SQL injection có thể là rất nghiêm trọng, bao gồm lộ thông tin nhạy cảm, xóa dữ liệu, thực thi mã độc hại và kiểm soát toàn bộ hệ thống.
Dưới đây là một số cách phòng tránh cuộc tấn công SQL injection:
* **Sử dụng prepared statements và parameterized queries** 
Sử dụng prepared statements hoặc parameterized queries để thực hiện truy vấn SQL. Điều này giúp ngăn chặn kẻ tấn công chèn các câu lệnh SQL vào dữ liệu đầu vào, vì các tham số đầu vào được truyền riêng biệt và không được kết hợp với câu lệnh SQL.
* **Kiểm tra và xử lý đầu vào từ người dùng**
* **Hạn chế quyền truy cập của người dùng đến cơ sở dữ liệu**


***
 **Cách tăng hiệu suất truy vấn Mysql**
Trong một số trường hợp, tôi đã gặp vấn đề về hiệu suất khi thực hiện các truy vấn SQL phức tạp hoặc khi có quá nhiều kết nối đến database. Để xử lý vấn đề này, tôi đã tối ưu hóa các truy vấn SQL, sử dụng indexes, và sử dụng các kỹ thuật caching. Đồng thời, tôi cũng kiểm tra và đảm bảo rằng số lượng kết nối đến database không vượt quá giới hạn được thiết lập.
Tối ưu hóa các truy vấn SQL:
* Chỉ lấy dữ liệu cần thiết: Sử dụng câu lệnh SQL SELECT chỉ để trả về các cột cần thiết, tránh lấy dữ liệu không cần thiết.
* Sử dụng indexes: Tạo indexes trên các cột được sử dụng trong điều kiện WHERE, ORDER BY, GROUP BY để tăng tốc độ truy xuất dữ liệu.
* Giới hạn số lượng kết quả: Sử dụng LIMIT để giới hạn số lượng kết quả trả về nếu chỉ cần một số ít kết quả.
* Tối ưu hóa JOINs: Sử dụng INNER JOIN, LEFT JOIN, RIGHT JOIN phù hợp và kiểm tra cách cung cấp các điều kiện JOIN để tránh truy vấn không hiệu quả.
* Đánh chỉ mục cho các cột dữ liệu thường xuyên được sử dụng: Các cột thường xuyên được sử dụng trong điều kiện tìm kiếm hoặc sắp xếp nên được chỉ mục để tăng hiệu suất truy vấn.

## Transaction 
Một transaction trong MySQL là một chuỗi các câu lệnh SQL được thực thi một cách nguyên tử, có nghĩa là tất cả các thao tác trong transaction được thực hiện hoặc không được thực hiện cùng một lúc. Điều này đảm bảo tính toàn vẹn của dữ liệu trong cơ sở dữ liệu, đặc biệt là trong các tình huống mà nhiều thao tác cần phải được thực hiện một cách liên tục và không thể bị gián đoạn. 
> Sử dụng hàm Begin() để bắt đầu một transaction mới, sau đó thực hiện các câu lệnh SQL trong transaction. Nếu bất kỳ lỗi nào xảy ra, chúng ta sẽ sử dụng Rollback() để quay lại trạng thái trước khi transaction được bắt đầu. Cuối cùng, chúng ta sử dụng Commit() để xác nhận và lưu trữ các thay đổi vào cơ sở dữ liệu nếu không có lỗi nào xảy ra.

## Concurrency
1. Race conditions: Khi nhiều goroutines thực hiện các thao tác đối với cùng một dữ liệu, có thể xảy ra race conditions nếu không đảm bảo sự đồng bộ hóa đúng đắn. Điều này có thể dẫn đến dữ liệu không nhất quán hoặc thậm chí là dữ liệu bị hỏng.
2. Deadlocks: Sử dụng transactions và locks có thể dẫn đến deadlocks khi nhiều goroutines cố gắng thực hiện các thao tác trên các bảng hoặc hàng dữ liệu cùng một lúc mà không tuân thủ thứ tự xác định.

**Cách khắc phục**
* Sử dụng Locks và Mutexes
> var wg sync.WaitGroup  var mu sync.Mutex // Khởi tạo một mutex   wg.Wait()
* Sử Dụng Channels và Context
>  <-ctx.Done()

