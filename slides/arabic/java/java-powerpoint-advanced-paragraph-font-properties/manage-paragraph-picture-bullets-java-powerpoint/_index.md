---
"description": "تعرّف على كيفية إضافة نقاط صور مخصصة إلى شرائح PowerPoint باستخدام Aspose.Slides لجافا. اتبع هذا الدليل المفصل خطوة بخطوة لدمج سلس."
"linktitle": "إدارة نقاط صور الفقرات في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إدارة نقاط صور الفقرات في Java PowerPoint"
"url": "/ar/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إدارة نقاط صور الفقرات في Java PowerPoint

## مقدمة
يُعد إنشاء عروض تقديمية جذابة وجذابة مهارةً أساسيةً في عالم الأعمال الحديث. يمكن لمطوري جافا الاستفادة من Aspose.Slides لتحسين عروضهم التقديمية بإضافة صور نقطية مخصصة في شرائح PowerPoint. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، مما يضمن لك إمكانية إضافة الصور النقطية إلى عروضك التقديمية بثقة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK)
- بيئة التطوير المتكاملة (IDE) مثل Eclipse أو IntelliJ IDEA
- مكتبة Aspose.Slides لـ Java
- المعرفة الأساسية ببرمجة جافا
- ملف صورة لصورة الرصاصة
لتنزيل مكتبة Aspose.Slides لـ Java، قم بزيارة [صفحة التحميل](https://releases.aspose.com/slides/java/). للحصول على التوثيق، راجع [التوثيق](https://reference.aspose.com/slides/java/).
## استيراد الحزم
أولاً، تأكد من استيراد الحزم اللازمة لمشروعك. أضف الحزم التالية في بداية ملف جافا:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
دعونا نقسم العملية إلى خطوات قابلة للإدارة.
## الخطوة 1: إعداد دليل المشروع الخاص بك
أنشئ مجلدًا جديدًا لمشروعك. سيحتوي هذا المجلد على ملف جافا، ومكتبة Aspose.Slides، وملف الصورة للرصاصة.
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: تهيئة العرض التقديمي
تهيئة مثيل جديد من `Presentation` هذا الكائن يمثل عرض PowerPoint الخاص بك.
```java
Presentation presentation = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة الأولى
انتقل إلى الشريحة الأولى من العرض التقديمي. الشرائح مفهرسة برقم صفر، لذا فإن الشريحة الأولى برقم صفر.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 4: تحميل صورة الرصاصة
حمّل الصورة التي تريد استخدامها للرصاصات. يجب وضعها في مجلد مشروعك.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## الخطوة 5: إضافة شكل تلقائي إلى الشريحة
أضف شكلاً تلقائياً إلى الشريحة. سيحتوي الشكل على النص مع النقاط المخصصة.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## الخطوة 6: الوصول إلى إطار النص
قم بالوصول إلى إطار النص الخاص بالشكل التلقائي للتحكم في فقراته.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## الخطوة 7: إزالة الفقرة الافتراضية
قم بإزالة الفقرة الافتراضية التي تتم إضافتها تلقائيًا إلى إطار النص.
```java
textFrame.getParagraphs().removeAt(0);
```
## الخطوة 8: إنشاء فقرة جديدة
أنشئ فقرة جديدة وحدد نصها. ستحتوي هذه الفقرة على صور نقطية مخصصة.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## الخطوة 9: تعيين نمط النقاط والصورة
قم بتعيين نمط الرصاصة لاستخدام الصورة المخصصة التي تم تحميلها مسبقًا.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## الخطوة 10: ضبط ارتفاع الرصاصة
قم بتعيين ارتفاع الرصاصة للتأكد من أنها تبدو جيدة في العرض التقديمي.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## الخطوة 11: إضافة الفقرة إلى إطار النص
أضف الفقرة التي تم إنشاؤها حديثًا إلى إطار النص الخاص بالشكل التلقائي.
```java
textFrame.getParagraphs().add(paragraph);
```
## الخطوة 12: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي بصيغة PPTX وPPT.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## خاتمة
وهذا كل ما في الأمر! باتباع هذه الخطوات، يمكنك بسهولة إضافة نقاط صور مخصصة إلى عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. توفر هذه المكتبة القوية مجموعة واسعة من الميزات لمساعدتك في إنشاء عروض تقديمية احترافية وجذابة بصريًا. لا تنسَ استكشاف [التوثيق](https://reference.aspose.com/slides/java/) لمزيد من الميزات المتقدمة وخيارات التخصيص.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة قوية تسمح لمطوري Java بإنشاء عروض PowerPoint وتعديلها والتلاعب بها برمجيًا.
### هل يمكنني استخدام أي صورة لنقاط الصورة؟
نعم، يمكنك استخدام أي صورة لنقاط الصورة طالما أنه من الممكن الوصول إليها من دليل المشروع الخاص بك.
### هل أحتاج إلى ترخيص لاستخدام Aspose.Slides لـ Java؟
يتطلب Aspose.Slides لجافا ترخيصًا لتشغيله بكامل وظائفه. يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/) أو شراء ترخيص كامل [هنا](https://purchase.aspose.com/buy).
### هل يمكنني إضافة فقرات متعددة بأنماط نقطية مختلفة في شكل تلقائي واحد؟
نعم، يمكنك إضافة فقرات متعددة ذات أنماط نقطية مختلفة إلى شكل تلقائي واحد عن طريق إنشاء كل فقرة وتكوينها بشكل فردي.
### أين يمكنني العثور على المزيد من الأمثلة والدعم؟
يمكنك العثور على المزيد من الأمثلة في [التوثيق](https://reference.aspose.com/slides/java/) واحصل على الدعم من مجتمع Aspose على [المنتديات](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}