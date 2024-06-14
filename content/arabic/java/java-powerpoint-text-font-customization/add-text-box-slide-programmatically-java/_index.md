---
title: إضافة مربع نص على الشريحة برمجياً باستخدام Java
linktitle: إضافة مربع نص على الشريحة برمجياً باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة مربع نص برمجيًا إلى شرائح PowerPoint باستخدام Aspose.Slides لـ Java. قم بتحسين إنتاجيتك باستخدام هذا الدليل التفصيلي.
type: docs
weight: 24
url: /ar/java/java-powerpoint-text-font-customization/add-text-box-slide-programmatically-java/
---
## مقدمة
يمكن أن يؤدي إنشاء عروض PowerPoint التقديمية ومعالجتها برمجيًا إلى تبسيط العديد من مهام سير العمل، بدءًا من إنشاء التقارير وحتى أتمتة العروض التقديمية. يوفر Aspose.Slides for Java واجهة برمجة تطبيقات قوية تتيح للمطورين أداء هذه المهام بكفاءة. في هذا البرنامج التعليمي، سنرشدك خلال إضافة مربع نص إلى شريحة باستخدام Aspose.Slides for Java. بحلول نهاية هذا البرنامج التعليمي، سيكون لديك فهم واضح لكيفية دمج هذه الوظيفة في تطبيقات Java الخاصة بك.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت مجموعة أدوات تطوير Java (JDK).
- IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/)
- المعرفة الأساسية ببرمجة جافا
## حزم الاستيراد
أولاً، قم باستيراد الحزم الضرورية من مكتبات Aspose.Slides وJava الأساسية لبدء البرمجة.
```java
import com.aspose.slides.*;
import java.io.File;
```
## الخطوة 1: قم بإعداد مشروعك
قم بإنشاء مشروع Java جديد في IDE الخاص بك وأضف مكتبة Aspose.Slides for Java إلى مسار إنشاء مشروعك. إذا لم تقم بتحميله بعد، قم بتحميله من[هنا](https://releases.aspose.com/slides/java/).
## الخطوة 2: تهيئة كائن العرض التقديمي
 تهيئة أ`Presentation` الكائن الذي يمثل ملف PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة وإضافة الشكل التلقائي
احصل على الشريحة الأولى من العرض التقديمي وأضف شكلاً تلقائيًا (مستطيلًا) إليها.
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## الخطوة 4: إضافة إطار نص إلى الشكل التلقائي
أضف إطار نص إلى الشكل التلقائي ليحتوي على نص.
```java
shape.addTextFrame(" ");
ITextFrame textFrame = shape.getTextFrame();
```
## الخطوة 5: تعيين محتوى النص
قم بتعيين محتوى النص داخل إطار النص.
```java
IParagraph para = textFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## الخطوة 6: حفظ العرض التقديمي
احفظ العرض التقديمي المعدل في ملف.
```java
pres.save(dataDir + "TextBox_out.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية إضافة مربع نص برمجيًا إلى شريحة باستخدام Aspose.Slides لـ Java. تسمح هذه الإمكانية للمطورين بأتمتة إنشاء عروض PowerPoint التقديمية وتخصيصها، مما يعزز الإنتاجية والكفاءة في التطبيقات المختلفة.
## الأسئلة الشائعة
### هل يستطيع Aspose.Slides لـ Java التعامل مع الأشكال الأخرى إلى جانب المستطيلات؟
نعم، يدعم Aspose.Slides الأشكال المختلفة مثل الدوائر والخطوط والمزيد.
### هل Aspose.Slides for Java مناسب لتطبيقات المؤسسات واسعة النطاق؟
بالتأكيد، فهو مصمم للتعامل مع المهام المعقدة بكفاءة.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides؟
 قم بزيارة[Aspose.Slides الوثائق](https://reference.aspose.com/slides/java/) للحصول على أدلة وأمثلة شاملة.
### كيف يمكنني الحصول على تراخيص مؤقتة للاختبار؟
 يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) من أسبوز.
### هل يدعم Aspose.Slides تحويل العروض التقديمية إلى تنسيقات أخرى؟
نعم، فهو يدعم تنسيقات مختلفة بما في ذلك PDF والصور.