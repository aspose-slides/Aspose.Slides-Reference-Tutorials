---
title: ملء الأشكال مع نمط في PowerPoint
linktitle: ملء الأشكال مع نمط في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعلم كيفية تعبئة الأشكال بالأنماط في PowerPoint باستخدام Aspose.Slides لـ Java. اتبع دليلنا السهل خطوة بخطوة لتحسين عروضك التقديمية بصريًا.
type: docs
weight: 11
url: /ar/java/java-powerpoint-shape-formatting-geometry/fill-shapes-pattern-powerpoint/
---
## مقدمة
يعد إنشاء عروض تقديمية جذابة بصريًا أمرًا ضروريًا لجذب جمهورك. إحدى الطرق لتحسين شرائح PowerPoint الخاصة بك هي ملء الأشكال بالأنماط. في هذا البرنامج التعليمي، سنتعرف على خطوات ملء الأشكال بالأنماط باستخدام Aspose.Slides for Java. تم تصميم هذا الدليل للمطورين الذين يرغبون في الاستفادة من الميزات القوية في Aspose.Slides لإنشاء عروض تقديمية مذهلة برمجيًا.
## المتطلبات الأساسية
قبل الغوص في الكود، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على جهازك.
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- المعرفة الأساسية ببرمجة جافا.
## حزم الاستيراد
أولاً، لنستورد الحزم الضرورية المطلوبة لمثالنا.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## الخطوة 1: قم بإعداد مشروعك
قبل كتابة الكود، تأكد من إعداد مشروعك بشكل صحيح. قم بإنشاء مشروع Java جديد في IDE الخاص بك وأضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.
## الخطوة 2: إنشاء دليل المستندات
لإدارة ملفاتك بكفاءة، لنقم بإنشاء دليل حيث سنحفظ عرض PowerPoint التقديمي الخاص بنا.
```java
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs();
}
```
يتحقق هذا المقتطف من وجود الدليل ويقوم بإنشائه إذا لم يكن موجودًا.
## الخطوة 3: إنشاء مثيل لفئة العرض التقديمي
 بعد ذلك، نحتاج إلى إنشاء مثيل لـ`Presentation` class، الذي يمثل ملف PowerPoint الخاص بنا.
```java
Presentation pres = new Presentation();
```
يؤدي هذا إلى تهيئة كائن عرض تقديمي جديد سنستخدمه لإضافة شرائح وأشكال.
## الخطوة 4: الوصول إلى الشريحة الأولى
للبدء، نحتاج إلى الوصول إلى الشريحة الأولى في عرضنا التقديمي. هذا هو المكان الذي سنضيف فيه أشكالنا.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 5: إضافة شكل مستطيل
دعونا نضيف شكلاً مستطيلاً إلى شريحتنا. سيتم ملء هذا المستطيل بنمط.
```java
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
يضيف مقتطف الكود هذا مستطيلاً إلى الشريحة في الموضع والحجم المحددين.
## الخطوة 6: اضبط نوع التعبئة على النمط
الآن، نحن بحاجة إلى ضبط نوع التعبئة للمستطيل لدينا على تعبئة النمط.
```java
shape.getFillFormat().setFillType(FillType.Pattern);
```
## الخطوة 7: اختر نمط النمط
يوفر Aspose.Slides أنماطًا مختلفة للأنماط. في هذا المثال، سوف نستخدم نمط "التعريشة".
```java
shape.getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.Trellis);
```
## الخطوة 8: تعيين ألوان النمط
يمكننا تخصيص ألوان نمطنا. دعونا نضبط لون الخلفية على اللون الرمادي الفاتح واللون الأمامي على اللون الأصفر.
```java
shape.getFillFormat().getPatternFormat().getBackColor().setColor(Color.LIGHT_GRAY);
shape.getFillFormat().getPatternFormat().getForeColor().setColor(Color.YELLOW);
```
## الخطوة 9: احفظ العرض التقديمي
بعد إعداد الشكل الخاص بنا بالنمط المطلوب، نحتاج إلى حفظ العرض التقديمي في ملف.
```java
pres.save(dataDir + "RectShpPatt_out.pptx", SaveFormat.Pptx);
```
يؤدي هذا إلى حفظ العرض التقديمي في الدليل المحدد باسم الملف "RectShpPatt_out.pptx".
## الخطوة 10: تنظيف الموارد
من الممارسات الجيدة التخلص من كائن العرض التقديمي لتحرير الموارد.
```java
if (pres != null) pres.dispose();
```
## خاتمة
تهانينا! لقد نجحت في ملء شكل بنمط في شريحة PowerPoint باستخدام Aspose.Slides for Java. تتيح لك هذه المكتبة القوية إنشاء العروض التقديمية ومعالجتها بسهولة، مما يضيف لمسة احترافية إلى مشروعاتك.
 باتباع هذا الدليل التفصيلي، يمكنك تحسين عروضك التقديمية بأنماط مختلفة، مما يجعلها أكثر جاذبية وجاذبية بصريًا. للحصول على المزيد من الميزات المتقدمة وخيارات التخصيص، تأكد من مراجعة[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها في تطبيقات Java.
### كيف يمكنني الحصول على Aspose.Slides لجافا؟
 يمكنك تنزيل Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/slides/java/).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### هل يمكنني استخدام Aspose.Slides لـ Java لمعالجة العروض التقديمية الحالية؟
نعم، يتيح لك Aspose.Slides for Java فتح عروض PowerPoint التقديمية الحالية وتحريرها وحفظها.
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على الدعم من[منتدى دعم Aspose.Slides](https://forum.aspose.com/c/slides/11).