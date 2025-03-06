---
title: تعيين مرساة إطار النص في PowerPoint مع Java
linktitle: تعيين مرساة إطار النص في PowerPoint مع Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين نقاط ارتساء إطار النص في PowerPoint باستخدام Java باستخدام Aspose.Slides. تعزيز العروض التقديمية الخاصة بك.
weight: 13
url: /ar/java/java-powerpoint-text-font-customization/set-anchor-text-frame-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في هذا البرنامج التعليمي، سوف تتعلم كيفية تعيين مرساة إطار النص في عروض PowerPoint التقديمية باستخدام Java بمساعدة Aspose.Slides. يتيح لك تثبيت إطارات النص التحكم بدقة في موضع النص وسلوكه داخل الشكل، مما يضمن أن تكون شرائحك جذابة بصريًا ومهيكلة بشكل فعال.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/)
- الفهم الأساسي للغة برمجة Java والمفاهيم الموجهة للكائنات
## حزم الاستيراد
للبدء، قم بتضمين مكتبة Aspose.Slides الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: قم بإعداد مشروعك
تأكد من إعداد مشروع Java في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من إضافة ملف Aspose.Slides JAR إلى مسار إنشاء مشروعك.
## الخطوة 2: إنشاء كائن العرض التقديمي
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
يؤدي هذا إلى تهيئة كائن عرض تقديمي جديد لـ PowerPoint.
## الخطوة 3: الوصول إلى الشريحة وإضافة شكل
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
هنا، يتم إضافة شكل مستطيل إلى الشريحة بإحداثيات وأبعاد محددة.
## الخطوة 4: إضافة إطار نص إلى الشكل
```java
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAnchoringType(TextAnchorType.Bottom);
```
 تتم إضافة إطار نص إلى الشكل المستطيل، ويتم تعيين نوع الإرساء الخاص به على`Bottom`، مع التأكد من تثبيت النص في أسفل الشكل.
## الخطوة 5: أدخل النص في إطار النص
```java
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
يؤدي ذلك إلى إضافة محتوى النص إلى إطار النص وتطبيق التنسيق، مثل تعيين لون النص إلى اللون الأسود.
## الخطوة 6: احفظ العرض التقديمي
```java
presentation.save(dataDir + "AnchorText_out.pptx", SaveFormat.Pptx);
```
وأخيرًا، احفظ العرض التقديمي المعدل في موقع محدد على القرص الخاص بك.

## خاتمة
يعد تعيين مرساة إطار النص في PowerPoint باستخدام Java أمرًا ضروريًا لإنشاء عروض تقديمية جيدة التنظيم. باتباع هذه الخطوات والاستفادة من Aspose.Slides for Java، يمكنك إدارة موضع النص بكفاءة داخل الأشكال لتحسين المظهر المرئي والوضوح لشرائحك.

## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية تسمح لمطوري Java بإنشاء عروض PowerPoint التقديمية وقراءتها ومعالجتها وتحويلها.
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
 يمكنك الوصول إلى الوثائق[هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### هل يمكنني تجربة Aspose.Slides لـ Java مجانًا؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك زيارة منتدى الدعم[هنا](https://forum.aspose.com/c/slides/11) لأية استفسارات أو مساعدة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
