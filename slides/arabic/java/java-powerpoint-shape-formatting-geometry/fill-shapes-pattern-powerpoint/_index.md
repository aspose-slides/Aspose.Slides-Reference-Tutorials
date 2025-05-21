---
"description": "تعلم كيفية ملء الأشكال بأنماط في PowerPoint باستخدام Aspose.Slides لجافا. اتبع دليلنا السهل خطوة بخطوة لتحسين عروضك التقديمية بصريًا."
"linktitle": "ملء الأشكال بالنمط في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ملء الأشكال بالنمط في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-formatting-geometry/fill-shapes-pattern-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ملء الأشكال بالنمط في PowerPoint

## مقدمة
يُعد إنشاء عروض تقديمية جذابة بصريًا أمرًا أساسيًا لجذب انتباه جمهورك. إحدى طرق تحسين شرائح PowerPoint هي ملء الأشكال بالأنماط. في هذا البرنامج التعليمي، سنشرح خطوات ملء الأشكال بالأنماط باستخدام Aspose.Slides لجافا. صُمم هذا الدليل خصيصًا للمطورين الذين يرغبون في الاستفادة من ميزات Aspose.Slides القوية لإنشاء عروض تقديمية مذهلة برمجيًا.
## المتطلبات الأساسية
قبل الغوص في الكود، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على جهازك.
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- المعرفة الأساسية ببرمجة جافا.
## استيراد الحزم
أولاً، دعنا نستورد الحزم اللازمة المطلوبة لمثالنا.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## الخطوة 1: إعداد مشروعك
قبل كتابة الكود، تأكد من إعداد مشروعك بشكل صحيح. أنشئ مشروع جافا جديدًا في بيئة التطوير المتكاملة (IDE) لديك، وأضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.
## الخطوة 2: إنشاء دليل المستندات
لإدارة ملفاتك بكفاءة، دعنا ننشئ دليلًا سنحفظ فيه عرض PowerPoint الخاص بنا.
```java
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs();
}
```
يتحقق هذا المقطع من وجود الدليل ويقوم بإنشائه إذا لم يكن موجودًا.
## الخطوة 3: إنشاء مثيل لفئة العرض التقديمي
بعد ذلك، نحتاج إلى إنشاء مثيل لـ `Presentation` الفئة التي تمثل ملف PowerPoint الخاص بنا.
```java
Presentation pres = new Presentation();
```
يؤدي هذا إلى تهيئة كائن عرض تقديمي جديد سنستخدمه لإضافة الشرائح والأشكال.
## الخطوة 4: الوصول إلى الشريحة الأولى
للبدء، علينا الوصول إلى الشريحة الأولى من عرضنا التقديمي. هناك سنضيف الأشكال.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 5: إضافة شكل مستطيل
لنُضِف شكلًا مستطيلًا إلى شريحتنا. سيُملأ هذا المستطيل بنمط.
```java
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
تضيف مقتطفات التعليمات البرمجية هذه مستطيلاً إلى الشريحة في الموضع والحجم المحددين.
## الخطوة 6: اضبط نوع التعبئة على النمط
الآن، نحتاج إلى تعيين نوع التعبئة للمستطيل الخاص بنا إلى تعبئة نمطية.
```java
shape.getFillFormat().setFillType(FillType.Pattern);
```
## الخطوة 7: اختيار نمط النمط
يوفر Aspose.Slides أنماطًا متنوعة. في هذا المثال، سنستخدم نمط "Trellis".
```java
shape.getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.Trellis);
```
## الخطوة 8: تعيين ألوان النمط
يمكننا تخصيص ألوان نمطنا. لنضبط لون الخلفية إلى رمادي فاتح، ولون المقدمة إلى أصفر.
```java
shape.getFillFormat().getPatternFormat().getBackColor().setColor(Color.LIGHT_GRAY);
shape.getFillFormat().getPatternFormat().getForeColor().setColor(Color.YELLOW);
```
## الخطوة 9: حفظ العرض التقديمي
بعد إعداد الشكل بالنمط المطلوب، نحتاج إلى حفظ العرض التقديمي في ملف.
```java
pres.save(dataDir + "RectShpPatt_out.pptx", SaveFormat.Pptx);
```
يؤدي هذا إلى حفظ العرض التقديمي في الدليل المحدد باسم الملف "RectShpPatt_out.pptx".
## الخطوة 10: تنظيف الموارد
من الجيد التخلص من كائن العرض لتحرير الموارد.
```java
if (pres != null) pres.dispose();
```
## خاتمة
تهانينا! لقد نجحت في ملء شكل بنمط في شريحة PowerPoint باستخدام Aspose.Slides لجافا. تتيح لك هذه المكتبة القوية إنشاء العروض التقديمية والتحكم بها بسهولة، مما يضيف لمسة احترافية إلى مشاريعك.
باتباع هذا الدليل التفصيلي، يمكنك تحسين عروضك التقديمية بأنماط متنوعة، مما يجعلها أكثر جاذبية وجاذبية بصريًا. لمزيد من الميزات المتقدمة وخيارات التخصيص، تأكد من الاطلاع على [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية تتيح للمطورين إنشاء عروض PowerPoint ومعالجتها وتحويلها في تطبيقات Java.
### كيف يمكنني الحصول على Aspose.Slides لـ Java؟
يمكنك تنزيل Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/slides/java/).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### هل يمكنني استخدام Aspose.Slides لـ Java للتعامل مع العروض التقديمية الموجودة؟
نعم، يسمح لك Aspose.Slides for Java بفتح عروض PowerPoint الحالية وتحريرها وحفظها.
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
يمكنك الحصول على الدعم من [منتدى دعم Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}