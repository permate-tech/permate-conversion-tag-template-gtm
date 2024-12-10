# Permate Conversion Tag - Google Tag Manager

Sự kiện chuyển đổi của Permate được ghi nhận khi Conversion tag được đặt trong Thank You page hoặc trang xảy ra sự kiện của bạn. Với <b>Permate Conversion Tag</b>, bạn có thể dễ dàng theo dõi chuyển đổi của khách hàng trên website, hoàn toàn miễn phí với <i>Permate Global</i>.

## Tổng quan tài liệu tích hợp

<ol>
  <li>Nhập (Import) Permate Conversion Tag Template vào mẫu Google Tag Manager của bạn.</li>
  <li>Cài đặt Permate Conversion Tag vào danh sách Tag của bạn.</li>
  <li>Cấu hình <b>Variables/Biến</b> và nâng cao cho Permate Conversion Tag.</li>
</ol>

## 1. Nhập (Import) Permate Conversion Tag Template

<ol>
  <li>Đăng nhập vào tài khoản Google Tag Manager của bạn, chọn Account/Container tương ứng, chọn vào <b>Templates/Mẫu</b> sau đó chọn <b>New/Mới</b>.</li>
  <li>Click chọn vào dấu 3 chấm trên cùng bên phải, sau đó chọn <b>Import/Nhập</b>.</li>
  <li>Bạn cần tải về file <a href="https://github.com/PmHubDev/qa-pixel-google-tag-manager-template/blob/main/template.tpl"><b>template.tpl</b></a> sau đó nhập vào Template/Mẫu.</li>
  <li>Chọn Save/Lưu</li>

  ![GTM_Permate_Import_ConversionTag](https://github.com/user-attachments/assets/acef213d-79e6-4cda-a08d-5e1ffdda999d)
  ![GTM_Permate_ConversionTag_Template](https://github.com/user-attachments/assets/3b4df772-beaa-44e3-9c65-711778baf60a)
</ol>

## 2. Cài đặt Permate Conversion Tag

<ol>
  <li>Đăng nhập vào tài khoản Google Tag Manager của bạn, chọn Account/Container tương ứng, chọn vào <b>Tag/Thẻ</b> sau đó chọn <b>New/Mới</b>.</li>
  <li>Chọn vào <b>Tag Configuration/Cấu Hình Thẻ</b>.</li>
  <li>Tại mục <b>Custom/Tuỳ chỉnh</b> tìm <b>Permate Conversion Tag</b> của Permate. Nếu bạn không tìm thấy, hãy thực hiện Import ở bước 1.</li>

  ![GTM_Permate_ConversionTag_View](https://github.com/user-attachments/assets/e8a4ffa4-65ea-4a3e-a14d-c48031b0b1bf)
  <li>Thẻ này sẽ cần sử dụng Trigger kích hoạt sự kiện <b>Page View/Xem Trang</b>, áp dụng cho trang Thank You/Thanh toán thành công của bạn. Tham khảo mẫu cấu hình sau</li>

  ![GooogleTagManager_Trigger](https://github.com/user-attachments/assets/9572aa97-d630-4950-8cbc-968af9a0b330)
  <li>Đặt tên cho thẻ của bạn và lưu.</li>
</ol>

## 3. Cấu hình Variables/Biến và Nâng cao cho thẻ Conversion Tag

<ol>
  <li>Đăng nhập vào tài khoản Google Tag Manager của bạn, chọn Account/Container tương ứng, chọn vào <b>Tag/Thẻ</b> sau đó chọn thẻ <b>Permate Conversion Tag</b> vừa mới tạo ở bước 2.</li>
  <li>Tại mục <b>Tag Configuration/Cấu hình Thẻ</b>, bạn cần điền giá trị của <b>Input params/Nhập tham số</b> theo hướng dẫn sau:</li>
  <b>Bước 1:</b> Xác định tham số cần truyền về <i>Permate</i>. Tham khảo bảng:
  <table>
    <tr>
      <th>Tên tham số</th>
      <th>Kiểu dữ liệu</th>
      <th>Ý nghĩa</th>
      <th>Ví dụ</th>
    </tr>
    <tr>
      <td>Offer ID (Bắt buộc)</td>
      <td>Int</td>
      <td>ID Chiến dịch của bạn trên Permate</td>
      <td>offer_id=2685</td>
    </tr>
    <tr>
      <td>Event ID <b>(**)</b></td>
      <td>Int</td>
      <td>ID sự kiện của lượt chuyển đổi trên Permate</td>
      <td>event_id=10294</td>
    </tr>
    <tr>
      <td>Referral ID <b>(**)</b></td>
      <td>String</td>
      <td>ID bất kì định danh sự kiện chuyển đổi trên hệ thống của bạn</td>
      <td>referral_id={{promo_code}}</td>
    </tr>
    <tr>
      <td>External Conversion ID</td>
      <td>String</td>
      <td>ID đơn hàng của bạn. Bạn có thể theo dõi đối soát trên Permate thông qua mã đơn hàng</td>
      <td>external_conversion_id={{billing_id}}</td>
    </tr>
    <tr>
      <td>Click UUID</td>
      <td>String</td>
      <td>ID nhấp chuột của Permate</td>
      <td>click_uuid={{pm_click}}</td>
    </tr>
    <tr>
      <td>Sale Value (CPS)</td>
      <td>Float</td>
      <td>Số tiền mà khách hàng thực hiện thanh toán. Chỉ dùng tham số này cho sự kiện có mô hình thanh toán là CPS (Cost per Sale)</td>
      <td>sale_value={{sub_price}}</td>
    </tr>
    <tr>
      <td>Payout (CPA)</td>
      <td>Float</td>
      <td>Số tiền hoa hồng mà Partner được nhận. Chỉ dùng tham số này cho sự kiện có mô hình thanh toán là CPA/CPI</td>
      <td>payout={{commission}}</td>
    </tr>
    <tr>
      <td>Currency</td>
      <td>Enum</td>
      <td>Đơn vị tiền tệ bạn sử dụng (<b>Bắt buộc</b> nếu bạn sử dụng VND)</td>
      <td>currency=vnd</td>
    </tr>
    <tr>
      <td>Bonus</td>
      <td>Float</td>
      <td>Số tiền thưởng dành cho Partner cho mỗi lượt chuyển đổi</td>
      <td>bonus=10</td>
    </tr>
    <tr>
      <td>Sub 1</td>
      <td>String</td>
      <td>Biến mở rộng số 1.</td>
      <td>sub1_adv={{email_hashMD5}}</td>
    </tr>
    <tr>
      <td>Sub 2</td>
      <td>String</td>
      <td>Biến mở rộng số 2.</td>
      <td>sub2_adv={{name_hashMD5}}</td>
    </tr>
    <tr>
      <td>Sub 3</td>
      <td>String</td>
      <td>Biến mở rộng số 3.</td>
      <td>sub3_adv={{age_hashMD5}}</td>
    </tr>
    <tr>
      <td>Sub 4</td>
      <td>String</td>
      <td>Biến mở rộng số 4.</td>
      <td>sub4_adv={{city_hashMD5}}</td>
    </tr>
    <tr>
      <td>Sub 5</td>
      <td>String</td>
      <td>Biến mở rộng số 5.</td>
      <td>sub5_adv={{IP_hashMD5}}</td>
    </tr>
  </table>
  ℹ️<b>(**)</b>: Bắt buộc nếu Chiến dịch của bạn có trên 2 sự kiện chuyển đổi. Bạn cần lựa chọn Referral ID hoặc Event ID tuỳ thuộc vào ngữ cảnh bạn sử dụng.<br><br>
  <b>Bước 2:</b> Xác định nguồn giá trị tham số
  <table>
    <tr>
      <th>Nguồn</th>
      <th>Tham số</th>
    </tr>
    <tr>
      <td>(1) Trong chi tiết chiến dịch của Permate</td>
      <td>Offer ID, Event ID, Currency</td>
    </tr>
    <tr>
      <td>(2) Từ hệ thống của bạn</td>
      <td>Referral ID, External Conversion ID, Sale Value, Payout, Bonus, Sub 1, Sub 2, Sub 3, Sub 4, Sub 5</td>
    </tr>
    <tr>
      <td>(3) Từ trình duyệt của khách hàng</td>
      <td>Click UUID, Sub 1, Sub 2, Sub 3, Sub 4, Sub 5</td>
    </tr>
  </table>
  ℹ️(1): Giá trị cho các tham số này được gán cứng. Thông thường bạn chỉ cần lựa chọn 3 tham số này.<br>
  ℹ️(2), (3): Thông thường giá trị cho các tham số này sẽ thay đổi theo thời gian. Bạn có thể lựa chọn <b>Google Tag Variables</b> để cấu hình giá trị hoặc tham khảo <b>Mục 3.3</b> để xem hướng dẫn cấu hình ở trình duyệt khách hàng.<br><br>
  <b>Bước 3:</b> Kết hợp các tham số thành chuỗi, cách nhau bằng kí tự &. Sau đó bạn điền giá trị vào <b>Input params/Nhập tham số</b> tương tự ví dụ sau.<br>
  ↪️Ví dụ: currency=vnd&offer_id=2685&event_id=12345

  ![GTM_ConversionTag_InputParams](https://github.com/user-attachments/assets/54b9466c-7ee3-4dbb-9fd2-afeae0a98ab9)

  <b>Bước 4:</b> Chọn <b>Save/Lưu</b> và mọi thứ đã hoàn thành.
  <li>Hướng dẫn cấu hình truyền giá trị tham số về Permate từ trình duyệt khách hàng.</li>
  <b>Mục đích:</b> Các tham số động như ở <b>Mục 3.2 > Bước 2 > Nguồn (2), (3)</b> thường sẽ thay đổi dựa trên hành vi của khách hàng. Permate cung cấp 1 JavaScript Object tại trình duyệt cho phép bạn cấu hình các tham số này thuận tiện trên trình duyệt khách hàng.<br>
  ⏭️<b>Permate Variable JavaScript Object</b>:

  ```javascript
  pmVariable={
    sale_value=null,
    bonus=null,
    referral_id=null,
    external_conversion_id=null,
    click_uuid=null,
    payout=null,
    sub1_adv=null,
    sub2_adv=null,
    sub3_adv=null,
    sub4_adv=null,
    sub5_adv=null,
  }
  ```

  Hãy đảm bảo bạn đã gán giá trị cho các biến này trước khi Permate Conversion Tag được kích hoạt.<br>
  ↪️Ví dụ: Bạn có thể tạo 1 HTML Custom Tag có Tag firing priority bắt buộc lớn hơn **Permate Conversion Tag** đang tạo, với đoạn mã sau:

  ```javascript
  if (typeof pmVariable === 'undefined') {
      window.pmVariable = {
          sale_value=null,
          external_conversion_id=null,
          sub1_adv=null
      };
  }
  var priceElement = document.getElementById('sub-price');
  var billingIDElement = document.getElementById('billing-id');
  var uniqueID = document.getElementById('user-id');
  pmVariable.sale_value = priceElement?priceElement.value:null;
  pmVariable.sale_value = billingIDElement?billingIDElement.value:null;
  pmVariable.sub1_adv = uniqueID?uniqueID.value:null;
  ```
  
</ol>

## Tìm hiểu chi tiết hơn về Permate Conversion Tag
#### :arrow_right: Ghé thăm tại đây [Trung Tâm Trợ Giúp](https://permate.com/docs-category/brand-en/)
