---
"description": "تعلّم كيفية تعديل خصائص الخطوط في عروض PowerPoint التقديمية باستخدام جافا مع Aspose.Slides لجافا. خصّص الخطوط بسهولة مع هذا الدليل المفصّل."
"linktitle": "خصائص الخط في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "خصائص الخط في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-font-management/font-properties-powerpoint-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# خصائص الخط في PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية تعديل خصائص الخطوط في عروض PowerPoint التقديمية باستخدام جافا، وتحديدًا باستخدام Aspose.Slides لجافا. سنرشدك خلال كل خطوة، بدءًا من استيراد الحزم اللازمة وحتى حفظ عرضك التقديمي المعدّل. هيا بنا!
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من [هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides لـ Java JAR: قم بتنزيل مكتبة Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): يمكنك استخدام أي بيئة تطوير متكاملة Java من اختيارك، مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.

## استيراد الحزم
أولاً، دعنا نستورد الحزم اللازمة للعمل مع Aspose.Slides لـ Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إنشاء كائن عرض تقديمي
ابدأ بإنشاء `Presentation` الكائن الذي يمثل ملف PowerPoint الخاص بك:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "FontProperties.pptx");
```
## الخطوة 2: الوصول إلى الشرائح والعناصر النائبة
الآن، دعنا ننتقل إلى الشرائح والعناصر النائبة في العرض التقديمي الخاص بك:
```java
ISlide slide = pres.getSlides().get_Item(0);
ITextFrame tf1 = ((IAutoShape) slide.getShapes().get_Item(0)).getTextFrame();
ITextFrame tf2 = ((IAutoShape) slide.getShapes().get_Item(1)).getTextFrame();
```
## الخطوة 3: الوصول إلى الفقرات والأجزاء
بعد ذلك، سنصل إلى الفقرات والأجزاء داخل إطارات النص:
```java
IParagraph para1 = tf1.getParagraphs().get_Item(0);
IParagraph para2 = tf2.getParagraphs().get_Item(0);
IPortion port1 = para1.getPortions().get_Item(0);
IPortion port2 = para2.getPortions().get_Item(0);
```
## الخطوة 4: تحديد الخطوط الجديدة
قم بتحديد الخطوط التي تريد استخدامها للأجزاء:
```java
FontData fd1 = new FontData("Elephant");
FontData fd2 = new FontData("Castellar");
```
## الخطوة 5: تعيين خصائص الخط
تعيين خصائص الخط المختلفة مثل الغامق والمائل والملون:
```java
port1.getPortionFormat().setLatinFont(fd1);
port2.getPortionFormat().setLatinFont(fd2);
port1.getPortionFormat().setFontBold(NullableBool.True);
port2.getPortionFormat().setFontBold(NullableBool.True);
port1.getPortionFormat().setFontItalic(NullableBool.True);
port2.getPortionFormat().setFontItalic(NullableBool.True);
port1.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port1.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
port2.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port2.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Peru));
```
## الخطوة 6: حفظ العرض التقديمي المعدّل
وأخيرًا، احفظ العرض التقديمي المعدّل على القرص:
```java
pres.save(dataDir + "WelcomeFont_out.pptx", SaveFormat.Pptx);
```

## خاتمة
يُسهّل Aspose.Slides لجافا التعامل مع خصائص الخطوط في عروض PowerPoint التقديمية باستخدام جافا. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تخصيص الخطوط لتحسين المظهر المرئي لشرائحك.
## الأسئلة الشائعة
### هل يمكنني استخدام الخطوط المخصصة مع Aspose.Slides لـ Java؟
نعم، يمكنك استخدام الخطوط المخصصة عن طريق تحديد اسم الخط أثناء تعريف `FontData`.
### كيف يمكنني تغيير حجم الخط النصي في شريحة PowerPoint؟
يمكنك تعديل حجم الخط عن طريق ضبط `FontHeight` ممتلكات `PortionFormat`.
### هل يدعم Aspose.Slides for Java إضافة تأثيرات النص؟
نعم، يوفر Aspose.Slides for Java خيارات مختلفة لتأثيرات النص لتحسين العروض التقديمية الخاصة بك.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على مزيد من الدعم والموارد لـ Aspose.Slides لـ Java؟
يمكنك زيارة منتدى Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11) للدعم والتوثيق [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}