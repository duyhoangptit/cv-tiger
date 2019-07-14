# Html, Css, Js leaning

	+ Block(Khối) là các phẩn tử html khi tạo ra nó sở hữu một hàng riêng biệt. Có thể tùy chỉnh kích thước của block.
		div, h1, he, p, ul

	+ Inline(Nội dòng): là các phần tử html khi tạo ra nó có thể đứng trên cùng một hàng
		span, strong, a....

	`Khi căn chỉnh chiều rộng hoặc chiều cao thì chỉ có những thẻ block mới apply giá trị đó, còn các thẻ inline sẽ tùy thuộc vào giá trị trong thẻ`

	+ Thẻ div là một thẻ block được dùng để gộp nhóm nhiều phần tử lại thành một khu vực. Thường được dùng để tạo bố cục hoặc tạo một khu vực nào đó trong website.

	+ Box model là kỹ thuật để tinh chỉnh lại các phẩn thử box, trong box model có 4 thành phần chỉnh<br>

		Margin: Lề bên ngoài của box
		border: Viền của box
		Padding: Phần lót bên trong bõ ngăn cách với nội dung
		content: Phần nội dung bên trong box

	+ box-sizing: 
		content-box: giá trị mặc định
		border-box: Thì giá trị của box bằng kích thước của cha - padding - border

	* {
		box-sizing: border-box;
		-moz-box-sizing: border-box; // để cho fifox
		-webkit-box-sizing: border-box; // dánh cho google chorme, opera phiên bản cũ
	}


	+ line-height: 

# Flexbox css3

1. Thành phần chính trong flex box
	- container: là thành phần lớn bao quanh các phần tử bên trong, bạn sẽ thiết lập kiểu hiển thị inline hoặc kiểu sắp xếp theo chiều dọc.
		Khi đó, các item bên trong sẽ hiển thị dựa trên thiếp lập của container này.

	- item: Các phẩn tử con của container được gọi là item, ở item chúng ta có thể thiếp lập nó sẽ sử dụng bao nhiêu cột trong một container,
		hoặc thiết lập thứ tư hiển thị của item.


2. Thành phần phụ
	- main start, main end: Khi thiết lập flex box , điểm bắt đầu của container được gọi là main start và điểm kết thúc là main end. Điều này có nghĩa,
		các item bên trong sẽ hiển thị từ main start tới main end. Và chiều vuông góc của nó là cross start, cross end cũng có nghĩa tương tự nhưng vuông
		góc vs main start, main end.

	- main axits, cros axits: Trục này là trục chính để điều hướng các item sẽ hiển thị. Trục cross axits sẽ vuông góc với trục main axits.
		Có thể sử dụng flex-direction: để thay đổi trục hiển thị.

	- main size: Kích thước của item (chiều rộng hoặc dọc) dựa trên trục main axits;

	- cross size: 	Kích thước (rộng hoặc dọc) của mỗi item theo trục cross axits;


3. Các thuộc tính thông dụng trong flex box

	+ flex-direction: row | columm | row-reverse | column-reverse

		-row: (default)Chuyển trục main axis thành chiều ngang, nghĩa là hiển thị theo hàng.
		-colum: Chuyển trục main axis thành chiều dọc, nghĩa là hiển thị theo cột.
		-row-reverse: Hiển thị theo hàng nhưng đảo ngược vị trí các item.
		-column-reverse: Hiển thị theo cột nhưng đảo ngược vị trí các item.

	+ flex-wrap: Thuôc tính này cho phép container có thể bọc lại các item kể cả khi kích thước của item bị thay đổi, áp dụng cả chiều dọc của container và item.
		- nowrap: (default) Các phần tử cứ sắp xếp theo hướng chính, kể cả vượt ngoài khung container
		- wrap: Các phần tử xếp theo hướng chính, nếu vượt qua kích thước khung chứa theo hướng chính sẽ ngắt tạo ra luồng xếp tiếp theo.
		- wrap-reverse: Tương tự như wrap những hàng(cột) bố trí ngược lại

	+ order: Sắp xếp lại vị trí của item mà k làm thay đổi thứ tự item đó trong DOM.

# Thiết lập các phần tử con
	+ display:

		- inline-block, 
		- float: left: Điều kiện là chiều cao của các item phải đồng đều, khi sử dụng float: left thì thường đi kèm vs clear: both: thuộc tính này có thể thấy nó được sử dụng rất nhiều trong bootstrap3 với hệ thống grid chia layout.
		- flex: Sẽ mặc định toàn bộ chiều
		- inline-flex:

	+ flex-grow: set item nào thì item đó sẽ lấy phần tróng còn lại trong container đắp vào cho nó.
		- =1: thì sẽ lấy phần trống còn lại của container đắp vào cho nó
		- =2: thì sẽ lấy phần dữ lớn gấp đôi item có flex-grow=1

	+ flex-shrink: Mặc định các item đều có flex-shrink=1. Điều này có nghĩa là khi chúng ta thu nhỏ trình duyệt lại, các phần tủ đều co lại bằng nhau.
		Tuy nhiên giả sử muốn item nào co lại nhiều hơn thì tăng giá trị flex-shrink lên =2...


	+ flex-basis: Gán cho item một kích thước nhất định theo trục mà nó được sắp xếp

	+ flex: là cách viết tổng hợp của 3 thuộc tính: flex-grow, flex-shrink, flex-basic
			flex: 1 0 100px

	+ align-self: Căn chỉnh một phẩn tử trong hệ thống flex, align-self nhận các giá trị
		- stretch
		- flex-end
		- center
		- flex-start

	+ justify-content: Mặc định các item bên trong rải bắt đầu từ main start đến main end, tuy nhiên nếu container vẫn còn khoảng trống thì có thể dùng thuộc tính justify-content để điều chỉnh lại vị trí bắt đầu của nó.
		- flex-start:
		- flex-end:
		- center:
		- space-between:
		- space-around:

	+ align-items: Căn chỉnh phẩn tủ con theo hướng vuông góc hướng chính
		- stretch(defaut): phần tử con mở rộng kích thước tối đa(bằng với chiều cao hàng hoặc chiều rộng cột) của phần tử theo hướng vuông góc với hướng chính.
		- baseline: Các phần tử con bám theo đường baseline của hàng(cột)
		- center: đẩy các phần tử vào giữa hướng chính
		- space-around: không gian thừa theo hướng chính chia đều cho khoảng cách các phần tử
		- space-beetween: không gian thừa theo hướng chính chia đều cho khoảng cách các phần tủ(phần tử đầu và cuối sát mép khung)

	+ align-content: chỉ có hiệu lực khi nhiều hàng, nhiều cột
		- stretch(defaut):
		- baseline:
		- center: 
		- flex-start:
		- flex-end:
		- space-around:
		- space-beetween:


# Cách viết tắt các thẻ cho nhanh
	div.container>div.item.item${$}*k(k là hằng số)
