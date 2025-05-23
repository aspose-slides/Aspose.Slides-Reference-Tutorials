---
"date": "2025-04-18"
"description": "Tìm hiểu cách khóa hoặc mở khóa tỷ lệ khung hình bảng trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Hướng dẫn này bao gồm thiết lập, triển khai mã và ứng dụng thực tế."
"title": "Cách khóa và mở khóa tỷ lệ khung hình của bảng trong PowerPoint bằng Aspose.Slides cho Java"
"url": "/vi/java/tables/lock-unlock-table-aspect-ratio-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách khóa và mở khóa tỷ lệ khung hình của bảng trong PowerPoint bằng Aspose.Slides cho Java

## Giới thiệu

Bạn có đang gặp khó khăn trong việc duy trì bố cục bảng nhất quán trong các bài thuyết trình PowerPoint của mình không? Với khả năng khóa hoặc mở khóa tỷ lệ khung hình, việc quản lý cách thay đổi kích thước bảng trong quá trình chỉnh sửa trở nên dễ dàng. Hướng dẫn này hướng dẫn bạn cách sử dụng "Aspose.Slides for Java" để kiểm soát hiệu quả kích thước bảng. Bạn sẽ học không chỉ cách thao tác tỷ lệ khung hình mà còn cách tích hợp tính năng này vào quy trình trình bày rộng hơn.

**Những gì bạn sẽ học được:**
- Cách khóa và mở khóa tỷ lệ khung hình của bảng trong bài thuyết trình PowerPoint.
- Quá trình thiết lập Aspose.Slides cho Java bằng Maven, Gradle hoặc tải xuống trực tiếp.
- Triển khai mã từng bước với giải thích rõ ràng.
- Ứng dụng thực tế và cân nhắc về hiệu suất khi làm việc với các trình chiếu lớn.

Chúng ta hãy cùng tìm hiểu các điều kiện tiên quyết trước khi bắt đầu.

## Điều kiện tiên quyết

Để làm theo hướng dẫn này, hãy đảm bảo bạn có:
- **Bộ phát triển Java (JDK):** Phiên bản 16 trở lên được cài đặt trên máy của bạn.
- **Ý tưởng:** Bất kỳ IDE Java nào như IntelliJ IDEA hoặc Eclipse.
- **Maven/Gradle:** Nếu bạn chọn sử dụng trình quản lý gói cho các gói phụ thuộc.
- Hiểu biết cơ bản về lập trình Java và quen thuộc với chức năng bảng của PowerPoint.

## Thiết lập Aspose.Slides cho Java

### Thiết lập Maven
Để đưa Aspose.Slides vào dự án của bạn bằng Maven, hãy thêm phần phụ thuộc sau:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Thiết lập Gradle
Đối với những người sử dụng Gradle, hãy bao gồm điều này trong `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải xuống trực tiếp
Ngoài ra, hãy tải xuống phiên bản mới nhất từ [Aspose.Slides cho bản phát hành Java](https://releases.aspose.com/slides/java/).

#### Các bước xin cấp giấy phép
- **Dùng thử miễn phí:** Bắt đầu bằng bản dùng thử miễn phí để khám phá các chức năng cơ bản.
- **Giấy phép tạm thời:** Xin giấy phép tạm thời để truy cập đầy đủ tính năng trong quá trình đánh giá.
- **Giấy phép mua hàng:** Hãy cân nhắc mua giấy phép để sử dụng lâu dài, không bị gián đoạn.

Sau khi thiết lập môi trường và có được các giấy phép cần thiết, hãy khởi tạo Aspose.Slides trong ứng dụng Java của bạn như sau:

```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        // Mã của bạn ở đây...
    }
}
```

## Hướng dẫn thực hiện

### Tỷ lệ khung hình của bảng khóa/mở khóa

Tính năng này cho phép bạn duy trì hoặc điều chỉnh tỷ lệ khung hình của bảng trong bài thuyết trình, đảm bảo thiết kế và khả năng đọc nhất quán.

#### Truy cập vào một bảng
Bắt đầu bằng cách tải bài thuyết trình của bạn và truy cập vào bảng mong muốn:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ITable;

// Tải tệp trình bày.
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/pres.pptx");
ITable table = (ITable) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

#### Kiểm tra và sửa đổi tỷ lệ khung hình

Kiểm tra xem tỷ lệ khung hình có bị khóa không, sau đó chuyển đổi trạng thái của nó:

```java
// Kiểm tra trạng thái khóa tỷ lệ khung hình hiện tại.
boolean isLocked = table.getGraphicalObjectLock().getAspectRatioLocked();

// Đảo ngược trạng thái khóa tỷ lệ khung hình.
table.getGraphicalObjectLock().setAspectRatioLocked(!isLocked);
```

Tính năng chuyển đổi này cho phép điều chỉnh linh hoạt trong quá trình thiết kế của bạn.

#### Lưu thay đổi
Sau khi thực hiện thay đổi, hãy lưu bản trình bày đã cập nhật:

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/pres-out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}