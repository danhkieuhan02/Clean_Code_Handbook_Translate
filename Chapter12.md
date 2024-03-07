# Sự xuất hiện
## bởi Jeff Langr

![Image tilte_1](image/chapter12_image01.jpg)

## Làm sạch thông qua thiết kế nổi lên

Điều gì sẽ xảy ra nếu có bốn quy tắc đơn giản mà bạn có thể tuân theo để giúp bạn tạo ra những thiết kế tốt khi bạn làm việc? Điều gì sẽ xảy ra nếu bằng cách tuân theo những quy tắc này, bạn có được những hiểu biết sâu sắc về cấu trúc và thiết kế của mã nguồn của bạn, làm cho nó dễ dàng hơn để áp dụng các nguyên tắc như SRP và DIP?
Điều gì sẽ xảy ra nếu những quy tắc này thúc đẩy _sự xuất hiện_ của những thiết kế tốt?

Nhiều người trong chúng ta cảm thấy rằng bốn quy tắc _Thiết kế Đơn giản(1)_ của Kent Beck là rất hữu ích trong việc tạo ra phần mềm có thiết kế tốt.

Theo Kent, một thiết kế được gọi là đơn giản nếu nó tuân theo các quy tắc sau đây: 

* **Chạy được tất cả các lần kiểm thử.**
* **Không chứa sự trùng lặp.**
* **Diễn đạt được mục đích của lập trình viên.**
* **Giảm thiểu được số lượng class và phương thức**

Các quy tắc trên được sắp xếp theo thứ tự quan trọng.

## Quy tắc thiết kế đơn giản 1: Chạy tất cả các lần kiểm thử

Điều đầu tiên và quan trọng nhất, bản thiết kế phải tạo ra một hệ thống hoạt động như mong đợi. Một hệ thống có thể có những thiết kế hoàn hảo trên giấy, nhưng nếu không có cách đơn giản nào để xác minh rằng hệ thống thực sự hoạt động như dự định thì mọi nỗ lực trên giấy tờ đều có vấn đề. 

    Một hệ thống được kiểm tra toàn diện và vượt qua tất cả các bài kiểm tra mọi lúc là một hệ thống có thể kiểm tra được. Đây là một phát biểu hiển nhiên, nhưng nó cũng là lời phát biểu quan trọng. Các hệ thống không thể kiểm tra được không thể kiểm chứng được. Có thể cho rằng, một hệ thống không thể xác minh sẽ không bao giờ được triển khai.

    May mắn thay, việc làm cho hệ thống của chúng ta có thể kiểm tra được sẽ thúc đẩy chúng tôi hướng tới một thiết kế trong đó các class của chúng tôi
    là mục đích nhỏ và duy nhất. Việc kiểm tra các class tuân thủ SRP (Single Responsibility principle) sẽ dễ dàng hơn. Chúng ta viết càng nhiều bài kiểm thử, chúng ta sẽ càng tiếp tục thúc đẩy những thứ đơn giản hơn để kiểm thử. Vì vậy, việc đảm bảo hệ thống của chúng ta có thể kiểm thử đầy đủ hoàn toàn sẽ giúp ta tạo ra các thiết kế tốt hơn.

    Sự kết nối chặt chẽ làm cho việc viết các bài kiểm thử trở nên khó khăn. Vì vậy, tương tự như vậy, càng nhiều bài kiểm thử chúng ta viết, chúng ta càng sử dụng nhiều các nguyên tắc như DIP (Dependency Inversion Principle) và các công cụ như dependency injection, interfaces, và abstraction để giảm thiểu sự kết nối. Những thiết kế của chúng ta thậm chí càng được cải thiện hơn nữa.

    Đáng chú ý, theo một quy tắc đơn giản và rõ ràng nói rằng chúng ta cần phải có các lần kiểm thử và chạy chúng liên tục tác động đến sự tuân thủ của hệ thống của chúng ta đối với các mục tiêu OO chính là khớp nối thấp và độ gắn kết cao. Việc viết bài kiểm thử sẽ dẫn đến việc thiết kế tốt hơn. 

## Quy tắc thiết kế đơn giản 2: Tái câu trúc mã nguồn

Sau khi hoàn thành các lần kiểm thử, ta được quyền giữ cho code và class được sạch sẽ. Chúng ta sẽ làm điều này bằng cách tái cấu trúc code dần dần. Đối với mỗi dòng code mà ta thêm vào, ta tạm dừng và ngẫm nghĩ về thiết kế mới. Liệu chúng ta có đang làm suy thoái dòng code ấy? Nếu vậy, chúng ta sẽ làm sạch nó và  chạy các bản thử nghiệm để xác minh rằng chúng ta không phá hỏng điều gì cả. _Thực tế là chúng ta tiến hành các lần chạy thử nghiệm chỉ để gạt đi nỗi sợ rằng việc dọn dẹp các dòng code sẽ phá hỏng nó!_

    Trong bước tái cấu trúc này, chúng ta có thể áp dụng bất kì kiến thức nào về thiết kế phần mềm. Chúng ta có thể tăng cường sự gắn kết, giảm sự ghép nối, phân tách hệ thống, mô-đun hóa các phân tách của hệ thống, thu nhỏ các chức năng và lớp của chúng ta, chọn những cái tên hay hơn, và như thế. Đây cũng là nơi chúng tôi áp dụng ba quy tắc cuối cùng của thiết kế đơn giản: Loại bỏ sự trùng lặp, đảm bảo tính biểu cảm và giảm thiểu số lượng class và phương thức. 

## Sự trùng lặp

Sự trùng lặp chính là kẻ thù của một hệ thống được thiết kế tốt. Nó đại diện cho việc bổ sung, rủi ro bổ sung và cả sự phức tạp bổ sung không cần thiết. Sự trùng lặp được thể hiện dưới nhiều hình thức. Tất nhiên, các dòng code trông giống nhau thì đề là trùng lặp. Các dòng code tương tự nhau thường có thể được chỉnh sửa trông giống nhau hơn để có thể dễ dàng tái cấu trúng chúng. Và, sự trùng lặp còn có thể tồn tại ở hình thức khác như thực hiện lặp lặp trùng lặp. Ví dụ như, ta có hai phương thức trong class tập hợp:  

```java
    int size() {}
    boolean isEmpty() {}
```
Chúng ta có thể có từng cách triển khai riêng biệt cho từng phương thức. Phương thức _isEmpty_ có thể quản lý, theo dõi và cập nhật một giá trị boolean, trong khi size thì quản lý một bộ đếm. Hoặc, chúng ta có thể loại bỏ sự trùng lặp này bằng cách gắn _isEmpty_ vào định nghĩa của _size_: 
```java
 boolean isEmpty() {
   return 0 == size();
 }
```
Việc tạo ra một hệ thống sạch yêu cầu ý chí loại bỏ sự trùng lặp, ngay cả khi chỉ trong vài dòng code. Ví dụ, hãy xem xét đoạn code sau: 

```java
 public void scaleToOneDimension(
         float desiredDimension, float imageDimension) {
      if (Math.abs(desiredDimension - imageDimension) < errorThreshold)
         return;
      float scalingFactor = desiredDimension / imageDimension;
      scalingFactor = (float)(Math.floor(scalingFactor * 100) * 0.01f);
      RenderedOp newImage = ImageUtilities.getScaledImage(
         image, scalingFactor, scalingFactor);
      image.dispose();
      System.gc();
      image = newImage;
   }
   public synchronized void rotate(int degrees) {
      RenderedOp newImage = ImageUtilities.getRotatedImage(
         image, degrees);
      image.dispose();
      System.gc();
      image = newImage;
   }
```
Để giữ cho hệ thống này sạch sẽ, chúng ta nên loại bỏ một lượng nhỏ sự trùng lặp giữa các phương thức _scaleToOneDimension_ và _rotate_:  

```java 
 public void scaleToOneDimension( float desiredDimension, float imageDimension) {
      if (Math.abs(desiredDimension - imageDimension) < errorThreshold)
        return;
      float scalingFactor = desiredDimension/imageDimension;
      scalingFactor = (float)(Math.floor(scalingFactor * 100) * 0.01f);
         replaceImage(ImageUtilities.getScaledImage(
         image, scalingFactor, scalingFactor));
}

   public synchronized void rotate(int degrees) {
        replaceImage(ImageUtilities.getRotatedImage(image, degrees));
   }
   private void replaceImage(RenderedOp newImage) {
        image.dispose();
        System.gc();
        image = newImage;
   }
```
Ngay khi ta trích xuất sự tương đồng ở mức độ thấp nhất, ta bắt đầu nhận ra các hành vi vi phạm **Nguyên lý Đơn nhiệm (SRP)**. Vì vậy, chúng ta có thể di chuyển một phương thức mới được trích xuất sang một lớp khác. Điều này nâng cao khả năng hiển thị của nó. Ai đó trong nhóm có thể nhận ra cơ hội để trừu tượng hóa phương thức mới này và tái sử dụng lại nó trong ngữ cảnh khác. Việc “tái sử dụng ở quy mô nhỏ” này có thể giúp giảm đáng kể độ phức tạp của hệ thống. Hiểu cách đạt được việc tái sử dụng trong quy mô nhỏ là điều cần thiết để đạt được việc tái sử dụng trong quy mô lớn.  

Mẫu **TEMPLATE METHOD(2)** là một kỹ thuật phổ biến để loại bỏ sự trùng lặp ở mức độ cao hơn. Lấy ví dụ: 
```java
public class VacationPolicy {
   public void accrueUSDivisionVacation() {
      // code to calculate vacation based on hours worked to date
      // ...
      // code to ensure vacation meets US minimums
      // ...
      // code to apply vaction to payroll record
      // ...
   }
   public void accrueEUDivisionVacation() {
      // code to calculate vacation based on hours worked to date
      // ...
      // code to ensure vacation meets EU minimums
      // ...
      // code to apply vaction to payroll record
      // ...
   }
 }
```
Đoạn code giữa hai phần *accrueUSDivisionVacation* và *accrueEuropeanDivisionVacation* phần lớn có sự tương đồng, ngoại trừ việc tính toán giới hạn hợp pháp. Phần thay đổi này dựa trên loại nhân viên(?).  

Chúng ta có thể loại bỏ sự trùng lặp hiển nhiên này bằng cách áp dụng mẫu **TEMPLATE METHOD**. 
```java
abstract public class VacationPolicy {
   public void accrueVacation() {
      calculateBaseVacationHours();
          alterForLegalMinimums();
      applyToPayroll();
   }
   private void calculateBaseVacationHours() { /* ... */ };
   abstract protected void alterForLegalMinimums();
   private void applyToPayroll() { /* ... */ };
 }

 public class USVacationPolicy extends VacationPolicy {
   @Override protected void alterForLegalMinimums() {
      // US specific logic
   }
 }

 public class EUVacationPolicy extends VacationPolicy {
   @Override protected void alterForLegalMinimums() {
      // EU specific logic
   }
 }
```
Các lớp con điền vào "lỗ" trong thuật toán _accrueVacation_, cung cấp những thông tin duy nhất không bị lặp lại.   

Đa số chúng ta đã từng trải qua việc làm việc với những đoạn code phức tạp. Nhiều người trong chúng ta cũng đã từng tạo ra một số đoạn code phức tạp ấy. Việc viết code mà _chúng ta_ hiểu rất dễ dàng, bởi vì vào thời điểm chúng ta viết nó, chúng ta hiểu sâu sắc vấn đề mà chúng ta đang cố gắng giải quyết. Những người bảo trì code sau này không thể có sự hiểu biết sâu sắc như vậy.

