---
title: تعبئة الأشكال بلون خالص في برنامج PowerPoint
linktitle: تعبئة الأشكال بلون خالص في برنامج PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعبئة الأشكال بألوان ثابتة في PowerPoint باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة للمطورين.
weight: 13
url: /ar/java/java-powerpoint-shape-formatting-geometry/fill-shapes-solid-color-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
إذا كنت قد عملت من قبل مع عروض PowerPoint التقديمية، فأنت تعلم أن إضافة الأشكال وتخصيص ألوانها يمكن أن يكون جانبًا حاسمًا في جعل شرائحك جذابة بصريًا وغنية بالمعلومات. مع Aspose.Slides لـ Java، تصبح هذه العملية سهلة للغاية. سواء كنت مطورًا يتطلع إلى أتمتة إنشاء عروض PowerPoint التقديمية أو شخصًا مهتمًا بإضافة مجموعة من الألوان إلى شرائحك، فإن هذا البرنامج التعليمي سيرشدك خلال عملية ملء الأشكال بألوان ثابتة باستخدام Aspose.Slides لـ Java.
## المتطلبات الأساسية
قبل أن نتعمق في التعليمات البرمجية، هناك بعض المتطلبات الأساسية التي يجب توفرها:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: قم بتنزيل مكتبة Aspose.Slides for Java من[موقع أسبوز](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse ستجعل عملية التطوير الخاصة بك أكثر سلاسة.
4. المعرفة الأساسية بـ Java: الإلمام ببرمجة Java سيساعدك على فهم التعليمات البرمجية وتنفيذها بشكل فعال.

## حزم الاستيراد
لبدء استخدام Aspose.Slides لـ Java، تحتاج إلى استيراد الحزم الضرورية. وإليك كيف يمكنك القيام بذلك:
```java
import com.aspose.slides.*;

import java.awt.*;
```
## الخطوة 1: قم بإعداد مشروعك
 أولاً، تحتاج إلى إعداد مشروع Java الخاص بك وتضمين Aspose.Slides for Java في تبعيات مشروعك. إذا كنت تستخدم Maven، فأضف التبعية التالية إلى ملفك`pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace XX.X with the latest version -->
</dependency>
```
 إذا كنت لا تستخدم Maven، فقم بتنزيل ملف JAR من ملف[موقع أسبوز](https://releases.aspose.com/slides/java/) وإضافته إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة العرض التقديمي
 إنشاء مثيل لـ`Presentation` فصل. يمثل هذا الفصل عرض PowerPoint التقديمي الذي ستعمل معه.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة الأولى
بعد ذلك، تحتاج إلى الحصول على الشريحة الأولى من العرض التقديمي حيث ستضيف الأشكال الخاصة بك.
```java
// احصل على الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 4: إضافة شكل إلى الشريحة
الآن، دعونا نضيف شكل مستطيل إلى الشريحة. يمكنك تخصيص موضع الشكل وحجمه عن طريق ضبط المعلمات.
```java
// إضافة شكل تلقائي لنوع المستطيل
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
## الخطوة 5: اضبط نوع التعبئة على صلب
 لتعبئة الشكل بلون خالص، قم بتعيين نوع التعبئة على`Solid`.
```java
// اضبط نوع التعبئة على Solid
shape.getFillFormat().setFillType(FillType.Solid);
```
## الخطوة 6: اختيار وتطبيق اللون
اختر لونًا للشكل. هنا، نستخدم اللون الأصفر، ولكن يمكنك اختيار أي لون تريده.
```java
//اضبط لون المستطيل
shape.getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
```
## الخطوة 7: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل في ملف.
```java
// اكتب ملف PPTX على القرص
presentation.save(dataDir + "RectShpSolid_out.pptx", SaveFormat.Pptx);
```

## خاتمة
وهناك لديك! لقد نجحت في ملء شكل بلون خالص في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. توفر هذه المكتبة مجموعة قوية من الميزات التي يمكن أن تساعدك في أتمتة عروضك التقديمية وتخصيصها بسهولة. سواء كنت تقوم بإنشاء تقارير، أو إنشاء مواد تعليمية، أو تصميم شرائح أعمال، يمكن أن يكون Aspose.Slides for Java أداة لا تقدر بثمن.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية للعمل مع عروض PowerPoint التقديمية في Java. يسمح لك بإنشاء العروض التقديمية وتعديلها وتحويلها برمجياً.
### كيف أقوم بتثبيت Aspose.Slides لـ Java؟
 يمكنك تنزيله من[موقع أسبوز](https://releases.aspose.com/slides/java/) وأضف ملف JAR إلى مشروعك، أو استخدم مدير التبعية مثل Maven لتضمينه.
### هل يمكنني استخدام Aspose.Slides لـ Java لتحرير العروض التقديمية الحالية؟
نعم، يتيح لك Aspose.Slides for Java فتح عروض PowerPoint التقديمية الحالية وتحريرها وحفظها.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[موقع أسبوز](https://releases.aspose.com/).
### أين يمكنني العثور على مزيد من الوثائق والدعم؟
 الوثائق التفصيلية متاحة على[موقع أسبوز](https://reference.aspose.com/slides/java/)، ويمكنك طلب الدعم على[اطرح المنتديات](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
