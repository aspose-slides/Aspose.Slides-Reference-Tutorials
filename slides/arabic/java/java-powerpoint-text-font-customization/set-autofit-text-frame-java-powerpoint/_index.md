---
"description": "تعرّف على كيفية ضبط ملاءمة إطارات النصوص تلقائيًا في جافا باوربوينت باستخدام Aspose.Slides لجافا. أنشئ عروضًا تقديمية ديناميكية بسهولة."
"linktitle": "تعيين ملاءمة إطار النص تلقائيًا في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين ملاءمة إطار النص تلقائيًا في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين ملاءمة إطار النص تلقائيًا في Java PowerPoint

## مقدمة
في تطوير تطبيقات جافا، يُعدّ إنشاء عروض تقديمية ديناميكية وجذابة بصريًا باستخدام برمجيًا متطلبًا شائعًا. يوفر Aspose.Slides for Java مجموعة قوية من واجهات برمجة التطبيقات (APIs) لتحقيق ذلك بسهولة. من الميزات الأساسية ضبط الملاءمة التلقائية لإطارات النص، مما يضمن ضبط النص بدقة داخل الأشكال دون الحاجة إلى تعديلات يدوية. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، مستفيدًا من Aspose.Slides for Java لأتمتة ملاءمة النص في شرائح PowerPoint.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية:
- مجموعة تطوير Java (JDK) مثبتة على نظامك
- تم تنزيل Aspose.Slides لمكتبة Java والإشارة إليها في مشروع Java الخاص بك
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse
### استيراد الحزم
أولاً، تأكد من استيراد فئات Aspose.Slides الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إنشاء عرض تقديمي جديد
ابدأ بإنشاء عرض تقديمي جديد في PowerPoint حيث ستضيف شرائح وأشكالًا.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة لإضافة الأشكال
انتقل إلى الشريحة الأولى من العرض التقديمي حيث تريد إضافة شكل مع النص الملائم تلقائيًا.
```java
// الوصول إلى الشريحة الأولى 
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 3: إضافة شكل تلقائي (مستطيل)
أضف شكلًا تلقائيًا (مستطيلًا) إلى الشريحة عند إحداثيات وأبعاد محددة.
```java
// إضافة شكل تلقائي من نوع المستطيل
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## الخطوة 4: إضافة إطار نصي إلى المستطيل
أضف إطار نص إلى شكل المستطيل.
```java
// إضافة إطار نصي إلى المستطيل
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## الخطوة 5: ضبط الملاءمة التلقائية لإطار النص
قم بتعيين خصائص الملاءمة التلقائية لإطار النص لضبط النص استنادًا إلى حجم الشكل.
```java
// الوصول إلى إطار النص
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## الخطوة 6: إضافة نص إلى إطار النص
أضف محتوى نصيًا إلى إطار النص داخل الشكل.
```java
// إنشاء كائن الفقرة لإطار النص
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// إنشاء كائن جزء للفقرة
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## الخطوة 7: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل باستخدام إطار النص الملائم تلقائيًا.
```java
// حفظ العرض التقديمي
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية ضبط ملاءمة إطارات النصوص تلقائيًا في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides. باتباع هذه الخطوات، يمكنك أتمتة ملاءمة النصوص داخل الأشكال، مما يُحسّن قابلية القراءة وجمالية عروضك التقديمية برمجيًا.

## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات Java قوية تتيح للمطورين إنشاء عروض PowerPoint وقراءتها ومعالجتها وتحويلها.
### كيف يمكنني تنزيل Aspose.Slides لـ Java؟
يمكنك تنزيل Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/slides/java/).
### هل يمكنني تجربة Aspose.Slides لـJava مجانًا؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
يمكنك العثور على وثائق مفصلة لـ Aspose.Slides لـ Java [هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
يمكنك الحصول على دعم المجتمع والدعم المهني لـ Aspose.Slides for Java من [هنا](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}