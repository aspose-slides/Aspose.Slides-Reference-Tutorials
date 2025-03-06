---
title: إدارة التعداد النقطي لصورة الفقرة في Java PowerPoint
linktitle: إدارة التعداد النقطي لصورة الفقرة في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة صور نقطية مخصصة إلى شرائح PowerPoint باستخدام Aspose.Slides لـ Java. اتبع هذا الدليل المفصل خطوة بخطوة لتحقيق التكامل السلس.
weight: 11
url: /ar/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
يعد إنشاء عروض تقديمية جذابة وجذابة بصريًا مهارة حاسمة في عالم الأعمال الحديث. يمكن لمطوري Java الاستفادة من Aspose.Slides لتحسين عروضهم التقديمية من خلال صور نقطية مخصصة في شرائح PowerPoint. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، مما يضمن أنه يمكنك بثقة إضافة صور نقطية إلى عروضك التقديمية.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت مجموعة أدوات تطوير Java (JDK).
- بيئة التطوير المتكاملة (IDE) مثل Eclipse أو IntelliJ IDEA
- Aspose.Slides لمكتبة جافا
- المعرفة الأساسية ببرمجة جافا
- ملف الصورة للصورة الرصاصة
 لتنزيل مكتبة Aspose.Slides for Java، قم بزيارة[صفحة التحميل](https://releases.aspose.com/slides/java/) . للتوثيق، تحقق من[توثيق](https://reference.aspose.com/slides/java/).
## حزم الاستيراد
أولاً، تأكد من استيراد الحزم اللازمة لمشروعك. أضف الواردات التالية في بداية ملف Java الخاص بك:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
دعونا نقسم العملية إلى خطوات يمكن التحكم فيها.
## الخطوة 1: قم بإعداد دليل المشروع الخاص بك
قم بإنشاء دليل جديد لمشروعك. سيحتوي هذا الدليل على ملف Java الخاص بك ومكتبة Aspose.Slides وملف الصورة الخاص بالرمز النقطي.
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: تهيئة العرض التقديمي
 تهيئة مثيل جديد لـ`Presentation` فصل. يمثل هذا الكائن عرض PowerPoint التقديمي الخاص بك.
```java
Presentation presentation = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة الأولى
قم بالوصول إلى الشريحة الأولى من العرض التقديمي. الشرائح غير مفهرسة بصفر، لذا فإن الشريحة الأولى تكون عند الفهرس 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 4: قم بتحميل الصورة النقطية
قم بتحميل الصورة التي تريد استخدامها للتعداد النقطي. يجب وضع هذه الصورة في دليل المشروع الخاص بك.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## الخطوة 5: إضافة شكل تلقائي إلى الشريحة
إضافة شكل تلقائي إلى الشريحة. سيحتوي الشكل على النص مع النقاط المخصصة.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## الخطوة 6: الوصول إلى إطار النص
قم بالوصول إلى إطار النص الخاص بالشكل التلقائي لمعالجة فقراته.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## الخطوة 7: إزالة الفقرة الافتراضية
قم بإزالة الفقرة الافتراضية التي تتم إضافتها تلقائيًا إلى إطار النص.
```java
textFrame.getParagraphs().removeAt(0);
```
## الخطوة 8: إنشاء فقرة جديدة
إنشاء فقرة جديدة وتعيين نصها. ستحتوي هذه الفقرة على التعداد النقطي للصورة المخصصة.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## الخطوة 9: تعيين نمط التعداد النقطي والصورة
قم بتعيين نمط التعداد النقطي لاستخدام الصورة المخصصة التي تم تحميلها مسبقًا.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## الخطوة 10: ضبط ارتفاع الرصاصة
قم بتعيين ارتفاع الرمز النقطي للتأكد من أنه يبدو جيدًا في العرض التقديمي.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## الخطوة 11: إضافة الفقرة إلى إطار النص
أضف الفقرة التي تم إنشاؤها حديثًا إلى إطار النص الخاص بالشكل التلقائي.
```java
textFrame.getParagraphs().add(paragraph);
```
## الخطوة 12: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي كملف PPTX وPPT.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## خاتمة
 وهناك لديك! باتباع هذه الخطوات، يمكنك بسهولة إضافة صور نقطية مخصصة إلى عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java. توفر هذه المكتبة القوية مجموعة واسعة من الميزات لمساعدتك في إنشاء عروض تقديمية احترافية وجذابة بصريًا. لا تنسى استكشاف[توثيق](https://reference.aspose.com/slides/java/)لمزيد من الميزات المتقدمة وخيارات التخصيص.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية تسمح لمطوري Java بإنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها برمجياً.
### هل يمكنني استخدام أي صورة للتعداد النقطي للصورة؟
نعم، يمكنك استخدام أي صورة للتعداد النقطي للصور طالما أنه يمكن الوصول إليها من دليل المشروع الخاص بك.
### هل أحتاج إلى ترخيص لاستخدام Aspose.Slides لـ Java؟
 يتطلب Aspose.Slides for Java ترخيصًا للحصول على الوظائف الكاملة. يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/) أو شراء ترخيص كامل[هنا](https://purchase.aspose.com/buy).
### هل يمكنني إضافة فقرات متعددة بأنماط تعداد نقطي مختلفة في شكل تلقائي واحد؟
نعم، يمكنك إضافة فقرات متعددة بأنماط تعداد نقطي مختلفة إلى شكل تلقائي واحد عن طريق إنشاء كل فقرة وتكوينها على حدة.
### أين يمكنني العثور على المزيد من الأمثلة والدعم؟
 يمكنك العثور على المزيد من الأمثلة في[توثيق](https://reference.aspose.com/slides/java/) واحصل على الدعم من مجتمع Aspose على[المنتديات](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
