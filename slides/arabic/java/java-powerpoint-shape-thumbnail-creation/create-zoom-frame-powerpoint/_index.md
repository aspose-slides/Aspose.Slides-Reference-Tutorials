---
title: إنشاء إطار التكبير في PowerPoint
linktitle: إنشاء إطار التكبير في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء إطارات Zoom جذابة في PowerPoint باستخدام Aspose.Slides لـ Java. اتبع دليلنا لإضافة عناصر تفاعلية إلى عروضك التقديمية.
weight: 17
url: /ar/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
يعد إنشاء عروض PowerPoint التقديمية الجذابة فنًا، وفي بعض الأحيان، يمكن لأصغر الإضافات أن تحدث فرقًا كبيرًا. إحدى هذه الميزات هي Zoom Frame، الذي يسمح لك بتكبير شرائح أو صور معينة، وإنشاء عرض تقديمي ديناميكي وتفاعلي. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء إطار تكبير/تصغير في PowerPoint باستخدام Aspose.Slides لـ Java.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.
- المعرفة الأساسية ببرمجة جافا.
## حزم الاستيراد
للبدء، تحتاج إلى استيراد الحزم الضرورية في مشروع Java الخاص بك. ستوفر هذه الواردات إمكانية الوصول إلى وظائف Aspose.Slides المطلوبة لهذا البرنامج التعليمي.
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
// ضع اسم الملف
String resultPath = "ZoomFramePresentation.pptx";
// المسار إلى الصورة المصدر
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
    // قم بإنشاء خلفية للشريحة الثانية
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    // قم بإنشاء مربع نص للشريحة الثانية
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### إعداد الخلفية للشريحة الثالثة
```java
    // قم بإنشاء خلفية للشريحة الثالثة
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    // قم بإنشاء مربع نص للشريحة الثالثة
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## الخطوة 3: إضافة إطارات التكبير
الآن، دعونا نضيف إطارات التكبير/التصغير إلى العرض التقديمي. سنضيف إطار تكبير/تصغير واحد مع معاينة شريحة وآخر مع صورة مخصصة.
### إضافة إطار التكبير مع معاينة الشرائح
```java
    // أضف كائنات ZoomFrame مع معاينة الشرائح
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### إضافة إطار تكبير مع صورة مخصصة
```java
    // أضف كائنات ZoomFrame مع صورة مخصصة
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## الخطوة 4: تخصيص إطارات التكبير/التصغير
لجعل إطارات Zoom الخاصة بنا مميزة، سنقوم بتخصيص مظهرها.
### تخصيص إطار التكبير/التصغير الثاني
```java
    // قم بتعيين تنسيق إطار التكبير/التصغير لكائن ZoomFrame2
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### إخفاء الخلفية لإطار التكبير الأول
```java
    // لا تظهر الخلفية لكائن ZoomFrame1
    zoomFrame1.setShowBackground(false);
```
## الخطوة 5: حفظ العرض التقديمي
وأخيرا، نقوم بحفظ العرض التقديمي الخاص بنا إلى المسار المحدد.
```java
    // احفظ العرض التقديمي
    pres.save(resultPath, SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## خاتمة
يمكن أن يؤدي إنشاء إطارات تكبير/تصغير في PowerPoint باستخدام Aspose.Slides لـ Java إلى تحسين التفاعل والمشاركة في العروض التقديمية بشكل كبير. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة إضافة معاينات الشرائح والصور المخصصة كإطارات تكبير/تصغير، وتخصيصها لتناسب موضوع العرض التقديمي الخاص بك. عرض سعيد!
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint التقديمية ومعالجتها برمجيًا.
### كيف أقوم بتثبيت Aspose.Slides لـ Java؟
 يمكنك تنزيل Aspose.Slides لـ Java من[موقع إلكتروني](https://releases.aspose.com/slides/java/) وإضافته إلى تبعيات مشروعك.
### هل يمكنني تخصيص مظهر إطارات Zoom؟
نعم، يتيح لك Aspose.Slides تخصيص خصائص مختلفة لإطارات Zoom، مثل نمط الخط واللون ورؤية الخلفية.
### هل من الممكن إضافة الصور إلى Zoom Frames؟
قطعاً! يمكنك إضافة صور مخصصة إلى Zoom Frames من خلال قراءة ملفات الصور وإضافتها إلى العرض التقديمي.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
 يمكنك العثور على وثائق وأمثلة شاملة على الموقع[Aspose.Slides لصفحة وثائق Java](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
