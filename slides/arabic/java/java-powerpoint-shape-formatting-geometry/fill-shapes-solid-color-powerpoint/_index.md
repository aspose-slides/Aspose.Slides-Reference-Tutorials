---
"description": "تعلّم كيفية ملء الأشكال بألوان ثابتة في PowerPoint باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة للمطورين."
"linktitle": "ملء الأشكال بلون ثابت في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ملء الأشكال بلون ثابت في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-formatting-geometry/fill-shapes-solid-color-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ملء الأشكال بلون ثابت في PowerPoint

## مقدمة
إذا سبق لك العمل على عروض PowerPoint التقديمية، فأنت تعلم أن إضافة الأشكال وتخصيص ألوانها يُعدّ جانبًا أساسيًا لجعل شرائحك جذابة بصريًا وغنية بالمعلومات. مع Aspose.Slides لجافا، تُصبح هذه العملية في غاية السهولة. سواء كنت مطورًا يسعى لأتمتة إنشاء عروض PowerPoint التقديمية أو مهتمًا بإضافة لمسة لونية مميزة إلى شرائحك، سيرشدك هذا البرنامج التعليمي خلال عملية ملء الأشكال بألوان ثابتة باستخدام Aspose.Slides لجافا.
## المتطلبات الأساسية
قبل أن نتعمق في الكود، هناك بعض المتطلبات الأساسية التي يجب أن تكون موجودة:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides لـ Java: قم بتنزيل مكتبة Aspose.Slides لـ Java من [موقع Aspose](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): ستعمل بيئة التطوير المتكاملة مثل IntelliJ IDEA أو Eclipse على جعل عملية التطوير الخاصة بك أكثر سلاسة.
4. المعرفة الأساسية بلغة جافا: ستساعدك المعرفة ببرمجة جافا على فهم الكود وتنفيذه بشكل فعال.

## استيراد الحزم
لبدء استخدام Aspose.Slides لجافا، عليك استيراد الحزم اللازمة. إليك كيفية القيام بذلك:
```java
import com.aspose.slides.*;

import java.awt.*;
```
## الخطوة 1: إعداد مشروعك
أولاً، عليك إعداد مشروع جافا الخاص بك وتضمين Aspose.Slides for Java في تبعيات مشروعك. إذا كنت تستخدم Maven، فأضف التبعية التالية إلى: `pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace XX.X with the latest version -->
</dependency>
```
إذا كنت لا تستخدم Maven، فقم بتنزيل ملف JAR من [موقع Aspose](https://releases.aspose.com/slides/java/) وأضفه إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة العرض التقديمي
إنشاء مثيل لـ `Presentation` الصف. يمثل هذا الصف عرض PowerPoint الذي ستعمل عليه.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة الأولى
بعد ذلك، ستحتاج إلى الحصول على الشريحة الأولى من العرض التقديمي حيث ستضيف الأشكال الخاصة بك.
```java
// احصل على الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 4: إضافة شكل إلى الشريحة
الآن، لنُضِف شكلًا مستطيلًا إلى الشريحة. يُمكنك تخصيص موضع وحجم الشكل بتعديل المُعاملات.
```java
// إضافة شكل تلقائي من نوع المستطيل
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
## الخطوة 5: اضبط نوع التعبئة على صلب
لملء الشكل بلون ثابت، اضبط نوع التعبئة على `Solid`.
```java
// تعيين نوع التعبئة إلى صلب
shape.getFillFormat().setFillType(FillType.Solid);
```
## الخطوة 6: اختيار اللون وتطبيقه
اختر لونًا للشكل. هنا، نستخدم اللون الأصفر، ولكن يمكنك اختيار أي لون تريده.
```java
// ضبط لون المستطيل
shape.getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
```
## الخطوة 7: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل في ملف.
```java
// اكتب ملف PPTX على القرص
presentation.save(dataDir + "RectShpSolid_out.pptx", SaveFormat.Pptx);
```

## خاتمة
ها قد انتهيت! لقد نجحت في ملء شكل بلون ثابت في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. توفر هذه المكتبة مجموعة قوية من الميزات التي تساعدك على أتمتة عروضك التقديمية وتخصيصها بسهولة. سواء كنت تُنشئ تقارير، أو تُنشئ مواد تعليمية، أو تُصمم شرائح أعمال، فإن Aspose.Slides لجافا أداة قيّمة.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة فعّالة للعمل مع عروض PowerPoint التقديمية بلغة Java. تتيح لك إنشاء العروض التقديمية وتعديلها وتحويلها برمجيًا.
### كيف أقوم بتثبيت Aspose.Slides لـ Java؟
يمكنك تنزيله من [موقع Aspose](https://releases.aspose.com/slides/java/) وأضف ملف JAR إلى مشروعك، أو استخدم مدير التبعيات مثل Maven لتضمينه.
### هل يمكنني استخدام Aspose.Slides لـ Java لتحرير العروض التقديمية الموجودة؟
نعم، يسمح لك Aspose.Slides for Java بفتح عروض PowerPoint الحالية وتحريرها وحفظها.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [موقع Aspose](https://releases.aspose.com/).
### أين يمكنني العثور على مزيد من الوثائق والدعم؟
تتوفر وثائق مفصلة على [موقع Aspose](https://reference.aspose.com/slides/java/)ويمكنك طلب الدعم على [منتديات Aspose](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}