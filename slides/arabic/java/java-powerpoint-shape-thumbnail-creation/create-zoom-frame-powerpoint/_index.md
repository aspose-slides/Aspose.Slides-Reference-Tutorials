---
"description": "تعرّف على كيفية إنشاء إطارات تكبير/تصغير جذابة في PowerPoint باستخدام Aspose.Slides لجافا. اتبع دليلنا لإضافة عناصر تفاعلية إلى عروضك التقديمية."
"linktitle": "إنشاء إطار تكبير/تصغير في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء إطار تكبير/تصغير في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء إطار تكبير/تصغير في PowerPoint

## مقدمة
إنشاء عروض تقديمية جذابة في PowerPoint فنٌّ بحد ذاته، وأحيانًا تُحدث أصغر الإضافات فرقًا كبيرًا. من هذه الميزات إطار التكبير/التصغير، الذي يُتيح لك تكبير شرائح أو صور مُحددة، مما يُنشئ عرضًا تقديميًا ديناميكيًا وتفاعليًا. في هذا البرنامج التعليمي، سنشرح لك عملية إنشاء إطار التكبير/التصغير في PowerPoint باستخدام Aspose.Slides لجافا.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على نظامك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.
- المعرفة الأساسية ببرمجة جافا.
## استيراد الحزم
للبدء، عليك استيراد الحزم اللازمة لمشروع جافا. ستتيح لك هذه الاستيرادات الوصول إلى وظائف Aspose.Slides المطلوبة لهذا البرنامج التعليمي.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## الخطوة 1: إعداد العرض التقديمي
أولاً، نحتاج إلى إنشاء عرض تقديمي جديد وإضافة بضع شرائح إليه.
```java
// اسم ملف الإخراج
String resultPath = "ZoomFramePresentation.pptx";
// المسار إلى صورة المصدر
String imagePath = "Your Document Directory/aspose-logo.jpg";
Presentation pres = new Presentation();
try {
    // إضافة شرائح جديدة إلى العرض التقديمي
    ISlide slide2 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
    ISlide slide3 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
```
## الخطوة 2: تخصيص خلفيات الشرائح
نريد أن نجعل شرائحنا مميزة بصريًا عن طريق إضافة ألوان الخلفية.
### إعداد الخلفية للشريحة الثانية
```java
    // إنشاء خلفية للشريحة الثانية
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    // إنشاء مربع نص للشريحة الثانية
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### إعداد الخلفية للشريحة الثالثة
```java
    // إنشاء خلفية للشريحة الثالثة
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    // إنشاء مربع نص للشريحة الثالثة
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## الخطوة 3: إضافة إطارات التكبير
الآن، لنُضِف إطارات التكبير/التصغير إلى العرض التقديمي. سنُضيف إطارًا واحدًا مع معاينة الشريحة وآخر مع صورة مُخصَّصة.
### إضافة إطار التكبير/التصغير مع معاينة الشريحة
```java
    // إضافة كائنات ZoomFrame مع معاينة الشريحة
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### إضافة إطار تكبير مع صورة مخصصة
```java
    // إضافة كائنات ZoomFrame مع صورة مخصصة
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## الخطوة 4: تخصيص إطارات التكبير
لجعل إطارات التكبير الخاصة بنا مميزة، سنقوم بتخصيص مظهرها.
### تخصيص إطار التكبير/التصغير الثاني
```java
    // تعيين تنسيق إطار التكبير لكائن zoomFrame2
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### إخفاء الخلفية لإطار التكبير الأول
```java
    // عدم إظهار الخلفية لكائن zoomFrame1
    zoomFrame1.setShowBackground(false);
```
## الخطوة 5: حفظ العرض التقديمي
وأخيرًا، نحفظ عرضنا التقديمي في المسار المحدد.
```java
    // حفظ العرض التقديمي
    pres.save(resultPath, SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## خاتمة
إنشاء إطارات تكبير/تصغير في PowerPoint باستخدام Aspose.Slides لجافا يُحسّن بشكل كبير من تفاعلية عروضك التقديمية وتفاعلها. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة إضافة معاينات الشرائح والصور المخصصة كإطارات تكبير/تصغير، وتخصيصها لتناسب موضوع عرضك التقديمي. عرض تقديمي سعيد!
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint ومعالجتها برمجيًا.
### كيف أقوم بتثبيت Aspose.Slides لـ Java؟
يمكنك تنزيل Aspose.Slides لـ Java من [موقع إلكتروني](https://releases.aspose.com/slides/java/) وأضفه إلى تبعيات مشروعك.
### هل يمكنني تخصيص مظهر إطارات التكبير؟
نعم، يسمح لك Aspose.Slides بتخصيص خصائص مختلفة لإطارات التكبير، مثل نمط الخط واللون ورؤية الخلفية.
### هل من الممكن إضافة الصور إلى إطارات Zoom؟
بالتأكيد! يمكنك إضافة صور مخصصة إلى إطارات Zoom من خلال قراءة ملفات الصور وإضافتها إلى العرض التقديمي.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
يمكنك العثور على وثائق وأمثلة شاملة على [صفحة توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}