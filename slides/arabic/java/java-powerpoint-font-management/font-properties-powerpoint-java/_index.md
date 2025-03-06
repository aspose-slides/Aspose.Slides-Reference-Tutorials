---
title: خصائص الخط في PowerPoint مع جافا
linktitle: خصائص الخط في PowerPoint مع جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية التعامل مع خصائص الخط في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides for Java. قم بتخصيص الخطوط بسهولة باستخدام هذا الدليل التفصيلي خطوة بخطوة.
weight: 11
url: /ar/java/java-powerpoint-font-management/font-properties-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# خصائص الخط في PowerPoint مع جافا

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية التعامل مع خصائص الخط في عروض PowerPoint التقديمية باستخدام Java، وتحديدًا باستخدام Aspose.Slides for Java. سنرشدك خلال كل خطوة، بدءًا من استيراد الحزم الضرورية وحتى حفظ العرض التقديمي المعدل. دعونا الغوص في!
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java JAR: قم بتنزيل مكتبة Aspose.Slides for Java من[هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): يمكنك استخدام أي Java IDE من اختيارك، مثل IntelliJ IDEA أو Eclipse أو NetBeans.

## حزم الاستيراد
أولاً، لنستورد الحزم اللازمة للعمل مع Aspose.Slides لـ Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إنشاء كائن عرض تقديمي
 ابدأ بإنشاء ملف`Presentation` الكائن الذي يمثل ملف PowerPoint الخاص بك:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "FontProperties.pptx");
```
## الخطوة 2: الوصول إلى الشرائح والعناصر النائبة
الآن، دعنا نصل إلى الشرائح والعناصر النائبة في العرض التقديمي الخاص بك:
```java
ISlide slide = pres.getSlides().get_Item(0);
ITextFrame tf1 = ((IAutoShape) slide.getShapes().get_Item(0)).getTextFrame();
ITextFrame tf2 = ((IAutoShape) slide.getShapes().get_Item(1)).getTextFrame();
```
## الخطوة 3: الوصول إلى الفقرات والأجزاء
بعد ذلك، سنصل إلى الفقرات والأجزاء الموجودة داخل إطارات النص:
```java
IParagraph para1 = tf1.getParagraphs().get_Item(0);
IParagraph para2 = tf2.getParagraphs().get_Item(0);
IPortion port1 = para1.getPortions().get_Item(0);
IPortion port2 = para2.getPortions().get_Item(0);
```
## الخطوة 4: تحديد الخطوط الجديدة
حدد الخطوط التي تريد استخدامها للأجزاء:
```java
FontData fd1 = new FontData("Elephant");
FontData fd2 = new FontData("Castellar");
```
## الخطوة 5: تعيين خصائص الخط
قم بتعيين خصائص الخط المختلفة مثل الغامق والمائل واللون:
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
## الخطوة 6: احفظ العرض التقديمي المعدل
وأخيرًا، احفظ العرض التقديمي المعدل على القرص:
```java
pres.save(dataDir + "WelcomeFont_out.pptx", SaveFormat.Pptx);
```

## خاتمة
أصبح التعامل مع خصائص الخطوط في عروض PowerPoint التقديمية باستخدام Java أمرًا سهلاً باستخدام Aspose.Slides لـ Java. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تخصيص الخطوط لتحسين المظهر المرئي لشرائحك.
## الأسئلة الشائعة
### هل يمكنني استخدام خطوط مخصصة مع Aspose.Slides لـ Java؟
 نعم، يمكنك استخدام الخطوط المخصصة عن طريق تحديد اسم الخط أثناء تعريف`FontData`.
### كيف يمكنني تغيير حجم خط النص في شريحة PowerPoint؟
 يمكنك ضبط حجم الخط عن طريق ضبط`FontHeight` ملكية`PortionFormat`.
### هل يدعم Aspose.Slides for Java إضافة تأثيرات النص؟
نعم، يوفر Aspose.Slides for Java خيارات تأثيرات نصية متنوعة لتحسين العروض التقديمية الخاصة بك.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على مزيد من الدعم والموارد لـ Aspose.Slides لـ Java؟
 يمكنك زيارة منتدى Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11) للدعم والتوثيق[هنا](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
