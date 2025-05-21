---
"description": "تعلّم كيفية إضافة مربع نص برمجيًا إلى شرائح PowerPoint باستخدام Aspose.Slides لجافا. حسّن إنتاجيتك باتباع هذا الدليل المفصل."
"linktitle": "إضافة مربع نص إلى الشريحة برمجيًا باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة مربع نص إلى الشريحة برمجيًا باستخدام Java"
"url": "/ar/java/java-powerpoint-text-font-customization/add-text-box-slide-programmatically-java/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مربع نص إلى الشريحة برمجيًا باستخدام Java

## مقدمة
يُمكن لإنشاء عروض PowerPoint التقديمية ومعالجتها برمجيًا تبسيط العديد من مهام سير العمل، بدءًا من إنشاء التقارير ووصولًا إلى أتمتة العروض التقديمية. يوفر Aspose.Slides for Java واجهة برمجة تطبيقات قوية تُمكّن المطورين من أداء هذه المهام بكفاءة. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة مربع نص إلى شريحة باستخدام Aspose.Slides for Java. بنهاية هذا البرنامج التعليمي، ستفهم بوضوح كيفية دمج هذه الوظيفة في تطبيقات Java.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK)
- IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/)
- المعرفة الأساسية ببرمجة جافا
## استيراد الحزم
أولاً، قم باستيراد الحزم اللازمة من Aspose.Slides ومكتبات Java الأساسية لبدء الترميز.
```java
import com.aspose.slides.*;
import java.io.File;
```
## الخطوة 1: إعداد مشروعك
أنشئ مشروع جافا جديدًا في بيئة التطوير المتكاملة لديك، وأضف مكتبة Aspose.Slides لجافا إلى مسار بناء مشروعك. إذا لم تقم بتنزيلها بعد، فاحصل عليها من [هنا](https://releases.aspose.com/slides/java/).
## الخطوة 2: تهيئة كائن العرض التقديمي
تهيئة `Presentation` الكائن الذي يمثل ملف PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة وإضافة الشكل التلقائي
احصل على الشريحة الأولى من العرض التقديمي وأضف إليها شكلًا تلقائيًا (مستطيلًا).
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
تعيين محتوى النص داخل إطار النص.
```java
IParagraph para = textFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## الخطوة 6: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل في ملف.
```java
pres.save(dataDir + "TextBox_out.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، استكشفنا كيفية إضافة مربع نص برمجيًا إلى شريحة باستخدام Aspose.Slides لجافا. تتيح هذه الميزة للمطورين أتمتة إنشاء وتخصيص عروض PowerPoint التقديمية، مما يعزز الإنتاجية والكفاءة في مختلف التطبيقات.
## الأسئلة الشائعة
### هل يمكن لـ Aspose.Slides for Java التعامل مع أشكال أخرى بالإضافة إلى المستطيلات؟
نعم، يدعم Aspose.Slides أشكالاً مختلفة مثل الدوائر والخطوط والمزيد.
### هل Aspose.Slides for Java مناسب لتطبيقات المؤسسات واسعة النطاق؟
بالتأكيد، فهو مصمم للتعامل مع المهام المعقدة بكفاءة.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides؟
قم بزيارة [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/) للحصول على أدلة وأمثلة شاملة.
### كيف يمكنني الحصول على تراخيص مؤقتة للاختبار؟
يمكنك الحصول على [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) من Aspose.
### هل يدعم Aspose.Slides تحويل العروض التقديمية إلى تنسيقات أخرى؟
نعم، فهو يدعم تنسيقات مختلفة بما في ذلك PDF والصور.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}