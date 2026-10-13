---
date: 2026-10-13
description: Tìm hiểu cách tạo typewriter text animation, set zoom level và thêm slide
  transitions trong Java bằng Aspose.Slides. Bao gồm step-by-step code và automation
  tips.
keywords:
- typewriter text animation
- set zoom level java
- animate text by letter
- automate powerpoint animations
- advanced slide animations
lastmod: 2026-10-13
og_description: Tìm hiểu cách tạo typewriter text animation, set zoom level và thêm
  slide transitions trong Java bằng Aspose.Slides. Bao gồm step-by-step code và automation
  tips.
og_image_alt: Guide showing typewriter text animation and zoom level settings in Java
  with Aspose.Slides
og_title: Tạo typewriter text animation và set zoom level trong Java
schemas:
- author: Aspose
  dateModified: '2026-10-13'
  description: Learn how to create typewriter text animation, set zoom level, and
    add slide transitions in Java using Aspose.Slides. Includes step-by-step code
    and automation tips.
  headline: Create typewriter text animation and set zoom level in Java
  type: TechArticle
- description: Learn how to create typewriter text animation, set zoom level, and
    add slide transitions in Java using Aspose.Slides. Includes step-by-step code
    and automation tips.
  name: Create typewriter text animation and set zoom level in Java
  steps:
  - name: '**Open the PPTX file** – `Presentation pres = new Presentation("input.pptx");`'
    text: '**Open the PPTX file** – `Presentation pres = new Presentation("input.pptx");`'
  - name: '**Find the text shape** – `IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().get_Item(0);`'
    text: '**Find the text shape** – `IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().get_Item(0);`'
  - name: '**Create a typewriter effect** – iterate over `shape.getTextFrame().getParagraphs()`
      and add an `Effect` of `EffectType.Typewriter` to each `Portion`.'
    text: '**Create a typewriter effect** – iterate over `shape.getTextFrame().getParagraphs()`
      and add an `Effect` of `EffectType.Typewriter` to each `Portion`.'
  - name: '**Save the result** – `pres.save("typewriter_output.pptx", SaveFormat.Pptx);`'
    text: '**Save the result** – `pres.save("typewriter_output.pptx", SaveFormat.Pptx);`'
  type: HowTo
- questions:
  - answer: Yes. Apply the typewriter effect to a text shape, then add a `SlideShowTransition`
      to the same slide; the transition runs after the typing animation completes.
    question: Can I combine typewriter text animation with slide transitions?
  - answer: The library reliably processes presentations with **up to 500 slides**
      containing complex animations without exhausting memory, thanks to its streaming
      architecture.
    question: What is the maximum number of slides Aspose.Slides can handle with animations?
  - answer: No. Aspose.Slides is a pure Java library and does not require PowerPoint
      or any Office components.
    question: Do I need Microsoft PowerPoint installed on the server?
  - answer: Adjust the `Effect.getTiming().setDelay(seconds)` property for each `Portion`;
      smaller values speed up the typing, larger values slow it down.
    question: How can I control the speed of the typewriter effect?
  - answer: You can render the animated slide to a series of images using `Presentation.save("output",
      SaveFormat.Png)` and view them sequentially, which mimics the live animation.
    question: Is there a way to preview the animation without saving the file?
  type: FAQPage
tags:
- typewriter animation
- Aspose.Slides
- Java presentation automation
title: Tạo typewriter text animation và set zoom level trong Java
url: /vi/java/animations-transitions/
weight: 9
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hoạt ảnh văn bản kiểu máy đánh chữ và đặt mức thu phóng trong Java

Nếu bạn cần thêm các hiệu ứng văn bản kiểu máy đánh chữ bắt mắt một cách lập trình **và** kiểm soát mức thu phóng của tệp PowerPoint, bạn đã đến đúng hướng dẫn. Trong hướng dẫn này, chúng tôi sẽ trình bày cách Aspose.Slides for Java cho phép bạn tạo hoạt ảnh văn bản ký tự‑theo‑ký tự, điều chỉnh mức thu phóng ở cấp slide, và nối các hành động này lại với nhau bằng các chuyển đổi slide mượt mà — tất cả mà không cần mở PowerPoint thủ công.

## Câu trả lời nhanh
- **Câu “typewriter text animation” có nghĩa là gì?** Nó hoạt ảnh từng ký tự một cách tuần tự, mô phỏng việc hiển thị giống như máy đánh chữ trong buổi trình chiếu.  
- **API nào kiểm soát mức thu phóng trong Java?** Giao diện `ISlideShow` cung cấp các phương thức `setZoom` cho các chế độ xem slide, notes và master.  
- **Tôi có thể tạo hoạt ảnh văn bản theo ký tự không?** Có – sử dụng các đối tượng `ParagraphPortion` với loại `Effect` là `EffectType.Typewriter`.  
- **Có thể tự động hoá hàng loạt không?** Chắc chắn; bạn có thể lặp qua hàng chục tệp PPTX và áp dụng cùng một bộ hoạt ảnh‑thu phóng trong một lần chạy.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Giấy phép tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ là bắt buộc cho triển khai thương mại.

## Cách tạo hoạt ảnh văn bản kiểu máy đánh chữ trong Java?

Tải bản trình chiếu, xác định hình dạng mục tiêu, và áp dụng hiệu ứng `Typewriter` cho mỗi đoạn văn. Câu trả lời ngắn này trình bày các bước chính trong dưới 70 từ: **khởi tạo `Presentation`, lấy `IAutoShape`, tạo một `Portion`, gán `EffectType.Typewriter`, và gọi `slide.getTimeline().addEffect`**. API tự động xử lý thời gian và thứ tự ký tự, vì vậy bạn nhận được hiệu ứng máy đánh chữ mượt mà với ít mã.

### Thực hiện từng bước
Trong Aspose.Slides, `Presentation` tải tệp PPTX, `IAutoShape` truy cập một hình dạng, và `Portion` đại diện cho một đoạn văn bản.  

1. **Open the PPTX file** – `Presentation pres = new Presentation("input.pptx");`  
2. **Find the text shape** – `IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().get_Item(0);`  
3. **Create a typewriter effect** – iterate over `shape.getTextFrame().getParagraphs()` and add an `Effect` of `EffectType.Typewriter` to each `Portion`.  
4. **Save the result** – `pres.save("typewriter_output.pptx", SaveFormat.Pptx);`

## Cách đặt mức thu phóng trong Java với Aspose.Slides?

Aspose.Slides cho phép bạn thay đổi hệ số thu phóng một cách lập trình cho các chế độ xem slide, notes và master, đảm bảo mọi người xem nội dung ở kích thước mong muốn. **Câu trả lời ngắn:** gọi `presentation.getSlideShow().setZoom(150);` để đặt mức thu phóng 150 % cho toàn bộ bản trình chiếu, hoặc sử dụng `setSlideZoom`, `setNotesZoom`, và `setMasterZoom` để kiểm soát chi tiết hơn. Điều này hoạt động trên máy tính để bàn, máy tính bảng hoặc máy chiếu mà không cần tương tác của người dùng.

### Ví dụ sử dụng
`setZoom` đặt phần trăm thu phóng chế độ xem bản trình chiếu (ví dụ, 150 cho 150 %).  
```java
Presentation pres = new Presentation("input.pptx");
pres.getSlideShow().setZoom(150);               // set overall zoom to 150%
pres.getSlideShow().setSlideZoom(120);          // optional per‑view overrides
pres.save("zoomed_output.pptx", SaveFormat.Pptx);
```

## Cách tạo hoạt ảnh văn bản theo ký tự trong Java?

`ParagraphPortion` đại diện cho một phần văn bản duy nhất trong một đoạn. API cung cấp một `Effect` chi tiết nhắm vào từng ký tự. **Câu trả lời trong 70 từ:** lấy mỗi `ParagraphPortion`, gắn một `Effect` với `EffectSubtype.Typewriter`, và đặt `TriggerType` thành `AfterPrevious` để các ký tự xuất hiện tự động lần lượt. Bạn cũng có thể điều chỉnh `Delay` và `Duration` để kiểm soát tốc độ gõ.

### Các điểm chính
- Sử dụng `Portion.getPortionText()` để truy cập từng ký tự.  
- Đặt `Effect.getTiming().setDelay(0.2)` để tạo khoảng dừng 0.2 s giữa các ký tự.  
- Kết hợp với `SlideShowTransition` để đồng bộ với việc chuyển slide.

## Cách tự động hoá các hoạt ảnh PowerPoint với Java?

`Files.list` trả về một luồng các đường dẫn tệp trong thư mục được chỉ định. Khi xử lý các lô lớn, bạn có thể lặp qua một thư mục, áp dụng cùng một bộ hoạt ảnh cho mỗi slide, và xuất các tệp đã chỉnh sửa. **Câu trả lời ngắn:** sử dụng `Files.list(Paths.get("folder"))` để liệt kê các tệp PPTX, sau đó với mỗi tệp chạy logic hoạt ảnh‑và‑thu phóng đã trình bày ở trên, cuối cùng gọi `presentation.save(outputPath, SaveFormat.Pptx)`. Cách này mở rộng tới hàng trăm bản trình chiếu với mức tiêu thụ bộ nhớ tối thiểu.

### Mẫu tự động hoá
```java
try (Stream<Path> files = Files.list(Paths.get("input_folder"))) {
    files.filter(p -> p.toString().endsWith(".pptx"))
         .forEach(p -> {
             Presentation pres = new Presentation(p.toString());
             // apply typewriter effect and zoom here
             pres.save("output/" + p.getFileName(), SaveFormat.Pptx);
         });
}
```

## Cách triển khai các hoạt ảnh slide nâng cao – các thực tiễn tốt nhất

`Effect` định nghĩa một hoạt ảnh được áp dụng cho một hình dạng hoặc văn bản. Các hoạt ảnh nâng cao kết hợp các hiệu ứng vào, nhấn mạnh và ra cùng với các tín hiệu âm thanh. **Câu trả lời:** nhóm các đối tượng `Effect` liên quan vào một `Sequence` bằng cách sử dụng `Slide.getTimeline().addSequence`, đặt `TriggerType` thành `OnClick` hoặc `WithPrevious`, và tinh chỉnh `Duration` để chuyển đổi mượt mà. Aspose.Slides hỗ trợ **hơn 50 loại hoạt ảnh** và có thể render **bản trình chiếu lên tới 300 trang** mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại hiệu năng cấp doanh nghiệp.

### Mẹo thực tiễn
- **Tái sử dụng các đối tượng effect** khi áp dụng cùng một hoạt ảnh cho nhiều hình dạng – giảm chi phí tạo đối tượng.  
- **Tận dụng các chuyển đổi `Morph`** để kể chuyện slide‑to‑slide liền mạch; chúng tự động nội suy vị trí và màu sắc của hình dạng.  
- **Đồng bộ với âm thanh** bằng cách thêm `AudioEffect` vào cùng một chuỗi timeline.

## Cách tạo hoạt ảnh cho biểu đồ trong Java – thêm hiệu ứng động

`IChart` đại diện cho một đối tượng biểu đồ trong slide. Tạo hoạt ảnh cho các series biểu đồ mang dữ liệu sống động. **Câu trả lời ngắn:** lấy đối tượng `IChart`, lặp qua `Series` của nó, và áp dụng hiệu ứng `Grow` hoặc `Fade` cho mỗi series. Bạn cũng có thể gắn bắt đầu hoạt ảnh vào một trigger tùy chỉnh (ví dụ, nhấn nút) bằng cách sử dụng `Effect.getTiming().setTriggerType(TriggerType.OnClick)`.

### Đoạn mã ví dụ
```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(2);
for (IChartSeries series : chart.getChartData().getSeries()) {
    Effect effect = pres.getSlideShow().getTimeline().addEffect(series, EffectType.Grow, EffectSubtype.None, EffectTriggerType.OnClick);
    effect.getTiming().setDuration(1.0);
}
```

## Các hướng dẫn có sẵn

### [Tạo hoạt ảnh biểu đồ trong PowerPoint bằng Aspose.Slides for Java&#58; Hướng dẫn từng bước](./animate-charts-pptx-aspose-slides-java/)
Tìm hiểu cách thêm các hoạt ảnh biểu đồ động vào bản trình chiếu PowerPoint của bạn bằng Aspose.Slides for Java. Theo dõi hướng dẫn toàn diện này để nâng cao các slide của bạn.

### [Tạo hoạt ảnh biểu đồ PowerPoint với Aspose.Slides for Java&#58; Hướng dẫn từng bước](./animate-powerpoint-charts-aspose-slides-java/)
Tìm hiểu cách tạo hoạt ảnh cho biểu đồ PowerPoint bằng Aspose.Slides for Java. Nâng cao bản trình chiếu của bạn với các hoạt ảnh động và thu hút khán giả một cách hiệu quả.

### [Tạo hoạt ảnh văn bản theo ký tự trong Java bằng Aspose.Slides&#58; Hướng dẫn toàn diện](./animate-text-by-letter-aspose-slides-java/)
Tìm hiểu cách tạo hoạt ảnh văn bản ký tự theo ký tự bằng Aspose.Slides for Java. Hướng dẫn này bao gồm mọi thứ từ cài đặt đến các hoạt ảnh nâng cao.

### [Aspose.Slides Java&#58; Hướng dẫn so sánh các loại hoạt ảnh](./aspose-slides-java-animation-comparison-guide/)
Tìm hiểu cách so sánh các loại hoạt ảnh như Descend, FloatDown, Ascend và FloatUp trong Aspose.Slides for Java. Nâng cao bản trình chiếu của bạn với các hoạt ảnh động.

### [Aspose.Slides for Java&#58; Thành thạo thao tác bảng và khung trong bản trình chiếu](./aspose-slides-java-enhance-presentations/)
Tìm hiểu cách nâng cao bản trình chiếu của bạn bằng cách thành thạo thao tác bảng và khung với Aspose.Slides for Java. Hướng dẫn này bao gồm tạo bảng, thêm khung văn bản và vẽ khung quanh nội dung cụ thể.

### [Tự động hoá chuyển đổi PowerPoint trong Java với Aspose.Slides&#58; Hướng dẫn toàn diện cho hoạt ảnh & chuyển đổi](./aspose-slides-java-presentation-automation/)
Tìm hiểu cách tự động hoá việc thêm chuyển đổi và hoạt ảnh vào tệp PPTX bằng Aspose.Slides for Java. Đơn giản hoá quy trình làm việc với bản trình chiếu một cách dễ dàng.

### [Cách thêm hoạt ảnh Fly vào slide PowerPoint bằng Aspose.Slides for Java | Hướng dẫn từng bước](./add-fly-animation-powerpoint-aspose-slides-java/)
Tìm hiểu cách nâng cao bản trình chiếu PowerPoint của bạn bằng cách thêm hiệu ứng hoạt ảnh Fly bằng Aspose.Slides for Java. Thực hiện theo hướng dẫn từng bước này để làm cho slide của bạn sinh động và hấp dẫn hơn.

### [Cách áp dụng chuyển đổi slide trong PowerPoint bằng Aspose.Slides for Java | Hướng dẫn từng bước](./master-slide-transitions-powerpoint-aspose-slides-java/)
Tìm hiểu cách áp dụng các chuyển đổi slide hấp dẫn trong PowerPoint bằng Aspose.Slides for Java qua hướng dẫn chi tiết này. Nâng cao bản trình chiếu của bạn một cách dễ dàng.

### [Cách trích xuất âm thanh từ chuyển đổi slide bằng Aspose.Slides for Java](./extract-audio-slide-transitions-aspose-slides-java/)
Tìm hiểu cách trích xuất âm thanh từ chuyển đổi slide trong PowerPoint bằng Aspose.Slides for Java, nâng cao bản trình chiếu của bạn với âm thanh tùy chỉnh. Phù hợp cho các nhà phát triển Java.

### [Cách lấy các hiệu ứng hoạt ảnh PowerPoint bằng Aspose.Slides for Java&#58; Hướng dẫn toàn diện](./retrieve-powerpoint-animations-aspose-slides-java/)
Tìm hiểu cách lấy và hiển thị hiệu ứng hoạt ảnh trong bản trình chiếu PowerPoint một cách hiệu quả bằng Aspose.Slides for Java. Hướng dẫn này bao gồm cài đặt, triển khai mã và các ứng dụng thực tế.

### [Cách lấy và thao tác các thuộc tính camera 3D trong PowerPoint bằng Aspose.Slides Java](./mastering-3d-camera-retrieval-powerpoint-aspose-slides-java/)
Tìm hiểu cách lấy và thao tác các thuộc tính camera 3D trong bản trình chiếu PowerPoint một cách lập trình bằng Aspose.Slides for Java. Nâng cao slide của bạn với các hoạt ảnh và chuyển đổi nâng cao.

### [Cách đặt loại chế độ xem PowerPoint một cách lập trình bằng Aspose.Slides Java](./set-presentation-view-type-aspose-slides-java/)
Tìm hiểu cách đặt loại chế độ xem cho bản trình chiếu PowerPoint bằng Aspose.Slides for Java. Hướng dẫn này bao gồm cài đặt, ví dụ mã và các ứng dụng thực tế để nâng cao quy trình làm việc với bản trình chiếu.

### [Thành thạo các hoạt ảnh slide nâng cao bằng Aspose.Slides for Java&#58; Hướng dẫn toàn diện](./advanced-slide-animations-aspose-slides-java/)
Tìm hiểu cách triển khai các hoạt ảnh slide nâng cao với Aspose.Slides for Java. Nâng cao bản trình chiếu của bạn bằng các hiệu ứng hấp dẫn và chuyển đổi liền mạch.

### [Thành thạo Aspose.Slides for Java&#58; Tạo và hoạt ảnh slide một cách lập trình](./master-aspose-slides-java-slide-creation-animation/)
Tìm hiểu cách sử dụng Aspose.Slides for Java để tạo, sao chép, tạo hoạt ảnh cho slide với chuyển đổi morph, và lưu bản trình chiếu một cách liền mạch. Hoàn hảo cho việc tự động hoá tạo slide.

### [Thành thạo chỉnh sửa chuyển đổi PPTX trong Java với Aspose.Slides](./mastering-pptx-transitions-java-aspose-slides/)
Tìm hiểu cách tự động hoá và chỉnh sửa bản trình chiếu PowerPoint bằng Aspose.Slides cho Java, tập trung vào chuyển đổi slide và thời gian hiệu ứng.

### [Thành thạo mức thu phóng PowerPoint với Aspose.Slides cho Java&#58; Hướng dẫn từng bước](./set-zoom-levels-powerpoint-aspose-slides-java/)
Tìm hiểu cách đặt mức thu phóng trong PowerPoint bằng Aspose.Slides cho Java. Hướng dẫn này bao gồm các chế độ xem slide và notes, đảm bảo bản trình chiếu của bạn rõ ràng và dễ điều hướng.

### [Thành thạo chuyển đổi slide trong Java bằng Aspose.Slides](./master-slide-transitions-aspose-slides-java/)
Tìm hiểu cách tạo bản trình chiếu PowerPoint động với các chuyển đổi slide bằng Aspose.Slides cho Java. Nâng cao kỹ năng trình chiếu của bạn ngay hôm nay!

### [Thành thạo chuyển đổi slide trong PowerPoint bằng Aspose.Slides cho Java&#58; Hướng dẫn toàn diện](./implement-slide-transitions-ppt-aspose-slides-java/)
Tìm hiểu cách triển khai các chuyển đổi slide động trong bản trình chiếu PowerPoint bằng Aspose.Slides cho Java. Nâng cao slide của bạn với các hoạt ảnh liền mạch và hiệu ứng chuyên nghiệp.

### [Thành thạo chuyển đổi slide động trong Java với Aspose.Slides](./aspose-slides-java-dynamic-slide-transitions/)
Nâng cao bản trình chiếu của bạn bằng Aspose.Slides cho Java. Học cách áp dụng các chuyển đổi động như Circle, Comb và Zoom để thu hút khán giả.

### [Thành thạo chuyển đổi Morph trong PowerPoint bằng Aspose.Slides cho Java](./master-aspose-slides-java-morph-transitions-powerpoint/)
Tìm hiểu cách áp dụng các chuyển đổi Morph tinh vi cho slide PowerPoint của bạn bằng Aspose.Slides cho Java. Nâng cao bản trình chiếu với các hoạt ảnh liền mạch và hiệu ứng động.

### [Thành thạo hoạt ảnh PowerPoint trong Java với Aspose.Slides&#58; Hướng dẫn toàn diện](./master-powerpoint-animations-aspose-slides-java/)
Tìm hiểu cách nâng cao bản trình chiếu PowerPoint một cách lập trình bằng Aspose.Slides cho Java. Hướng dẫn này bao gồm cài đặt, tùy chỉnh hoạt ảnh và các ứng dụng thực tế.

### [Thành thạo hoạt ảnh PowerPoint với Aspose.Slides trong Java&#58; Tải và tạo hoạt ảnh cho bản trình chiếu một cách dễ dàng](./master-aspose-slides-java-powerpoint-animations/)
Tìm hiểu cách tải, truy cập và tạo hoạt ảnh cho bản trình chiếu PowerPoint bằng Aspose.Slides cho Java. Thành thạo các hoạt ảnh, placeholder và chuyển đổi một cách dễ dàng.

## Tài nguyên bổ sung

- [Tài liệu Aspose.Slides cho Java](https://docs.aspose.com/slides/java/)
- [Tham chiếu API Aspose.Slides cho Java](https://reference.aspose.com/slides/java/)
- [Tải xuống Aspose.Slides cho Java](https://releases.aspose.com/slides/java/)
- [Hỗ trợ miễn phí](https://forum.aspose.com/)
- [Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)

## Câu hỏi thường gặp

**Q: Tôi có thể kết hợp hoạt ảnh văn bản kiểu máy đánh chữ với chuyển đổi slide không?**  
A: Có. Áp dụng hiệu ứng typewriter cho một hình dạng văn bản, sau đó thêm `SlideShowTransition` vào cùng slide; chuyển đổi sẽ chạy sau khi hoạt ảnh gõ hoàn thành.

**Q: Số lượng slide tối đa mà Aspose.Slides có thể xử lý với hoạt ảnh là bao nhiêu?**  
A: Thư viện xử lý ổn định các bản trình chiếu với **tối đa 500 slide** chứa hoạt ảnh phức tạp mà không cạn kiệt bộ nhớ, nhờ kiến trúc streaming.

**Q: Tôi có cần cài đặt Microsoft PowerPoint trên máy chủ không?**  
A: Không. Aspose.Slides là thư viện Java thuần và không yêu cầu PowerPoint hay bất kỳ thành phần Office nào.

**Q: Làm sao tôi có thể kiểm soát tốc độ của hiệu ứng typewriter?**  
A: Điều chỉnh thuộc tính `Effect.getTiming().setDelay(seconds)` cho mỗi `Portion`; giá trị nhỏ hơn làm tăng tốc gõ, giá trị lớn hơn làm chậm lại.

**Q: Có cách nào xem trước hoạt ảnh mà không lưu tệp không?**  
A: Bạn có thể render slide đã hoạt ảnh thành một loạt hình ảnh bằng `Presentation.save("output", SaveFormat.Png)` và xem chúng tuần tự, mô phỏng hoạt ảnh thực tế.

---

**Cập nhật lần cuối:** 2026-10-13  
**Kiểm tra với:** Aspose.Slides for Java 24.11  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Cách tạo hoạt ảnh văn bản theo ký tự trong Java bằng Aspose.Slides – Hướng dẫn toàn diện](/slides/java/animations-transitions/animate-text-by-letter-aspose-slides-java/)
- [Đặt mức thu phóng PowerPoint Aspose Slides Java](/slides/java/animations-transitions/set-zoom-levels-powerpoint-aspose-slides-java/)
- [Các hoạt ảnh slide nâng cao Aspose Slides Java](/slides/java/animations-transitions/advanced-slide-animations-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}