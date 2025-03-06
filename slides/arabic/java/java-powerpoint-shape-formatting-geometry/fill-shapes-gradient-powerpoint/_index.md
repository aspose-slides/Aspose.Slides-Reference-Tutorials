---
title: ملء الأشكال مع التدرج في PowerPoint
linktitle: ملء الأشكال مع التدرج في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية ملء الأشكال بالتدرج في PowerPoint باستخدام Aspose.Slides لـ Java من خلال هذا الدليل المفصل خطوة بخطوة.
weight: 10
url: /ar/java/java-powerpoint-shape-formatting-geometry/fill-shapes-gradient-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ملء الأشكال مع التدرج في PowerPoint

## مقدمة
يعد إنشاء عروض PowerPoint التقديمية الجذابة بصريًا أمرًا بالغ الأهمية لجذب جمهورك. إحدى الطرق الفعالة لتحسين شرائحك هي ملء الأشكال بالتدرجات اللونية. سيرشدك هذا البرنامج التعليمي خلال عملية استخدام Aspose.Slides لـ Java لملء الأشكال بالتدرجات اللونية في PowerPoint. سواء كنت مطورًا متمرسًا أو بدأت للتو، ستجد هذا الدليل مفيدًا وسهل المتابعة. دعنا نتعمق في عالم التدرجات ونرى كيف يمكنها تحويل عروضك التقديمية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- Java Development Kit (JDK): تأكد من تثبيت JDK. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides لـ Java: قم بتنزيل أحدث إصدار من[هنا](https://releases.aspose.com/slides/java/).
- بيئة التطوير المتكاملة (IDE): بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse ستجعل تجربة البرمجة الخاصة بك أكثر سلاسة.
- المعرفة الأساسية بجافا: الإلمام ببرمجة جافا أمر ضروري.
## حزم الاستيراد
للبدء مع Aspose.Slides، تحتاج إلى استيراد الحزم الضرورية. تأكد من إضافة Aspose.Slides for Java إلى تبعيات مشروعك.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## الخطوة 1: إعداد دليل المشروع الخاص بك
أولاً، أنت بحاجة إلى دليل لحفظ ملف PowerPoint الخاص بك.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean isExists = new File(dataDir).exists();
if (!isExists)
	new File(dataDir).mkdirs();
```
تضمن هذه الخطوة وجود الدليل الذي تنوي حفظ ملف PowerPoint الخاص بك فيه. إذا لم يحدث ذلك، فسيقوم الكود بإنشائه لك.
## الخطوة 2: إنشاء مثيل لفئة العرض التقديمي
بعد ذلك، قم بإنشاء مثيل لفئة العرض التقديمي الذي يمثل ملف PowerPoint.
```java
// إنشاء فئة العرض التقديمي التي تمثل PPTX
Presentation pres = new Presentation();
```
سيكون هذا الكائن بمثابة حاوية للشرائح والأشكال الخاصة بك.
## الخطوة 3: الوصول إلى الشريحة الأولى
بعد إنشاء مثيل العرض التقديمي، تحتاج إلى الوصول إلى الشريحة الأولى حيث ستضيف الأشكال.
```java
// احصل على الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
```
يجلب هذا الرمز الشريحة الأولى من العرض التقديمي الخاص بك حيث يمكنك البدء في إضافة الأشكال.
## الخطوة 4: إضافة شكل القطع الناقص
الآن، قم بإضافة شكل بيضاوي إلى الشريحة.
```java
// إضافة شكل تلقائي لنوع القطع الناقص
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
هنا، يتم إضافة شكل بيضاوي في موضع محدد بأبعاد محددة.
## الخطوة 5: تطبيق تعبئة متدرجة على الشكل
لجعل الشكل جذابًا بصريًا، قم بتطبيق تعبئة متدرجة عليه.
```java
// قم بتطبيق بعض التنسيقات المتدرجة على شكل القطع الناقص
shp.getFillFormat().setFillType(FillType.Gradient);
shp.getFillFormat().getGradientFormat().setGradientShape(GradientShape.Linear);
```
يقوم هذا الكود بتعيين نوع تعبئة الشكل على التدرج ويحدد شكل التدرج على أنه خطي.
## الخطوة 6: تعيين اتجاه التدرج
حدد اتجاه التدرج للحصول على تأثير بصري أفضل.
```java
// ضبط اتجاه التدرج
shp.getFillFormat().getGradientFormat().setGradientDirection(GradientDirection.FromCorner2);
```
يؤدي هذا إلى ضبط التدرج على التدفق من زاوية إلى أخرى، مما يعزز المظهر الجمالي للشكل.
## الخطوة 7: إضافة توقفات التدرج
تحدد نقاط التوقف المتدرجة الألوان والمواضع داخل التدرج.
```java
// إضافة اثنين من توقفات التدرج
shp.getFillFormat().getGradientFormat().getGradientStops().add((float) 1.0, new Color(PresetColor.Purple));
shp.getFillFormat().getGradientFormat().getGradientStops().add((float) 0, Color.RED);
```
يضيف هذا الرمز نقطتي توقف متدرجتين، يمزجان من اللون الأرجواني إلى اللون الأحمر.
## الخطوة 8: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الخاص بك في الدليل المحدد.
```java
// اكتب ملف PPTX على القرص
pres.save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
يحفظ سطر التعليمات البرمجية هذا العرض التقديمي الخاص بك بتأثير التدرج المطبق.
## الخطوة 9: التخلص من كائن العرض التقديمي
تأكد دائمًا من تحرير الموارد عن طريق التخلص من كائن العرض التقديمي.
```java
finally {
	if (pres != null) pres.dispose();
}
```
وهذا يضمن تنظيف جميع الموارد بشكل صحيح.
## خاتمة
يمكن أن يؤدي استخدام التدرجات اللونية في أشكال PowerPoint إلى تحسين المظهر المرئي لعروضك التقديمية بشكل كبير. باستخدام Aspose.Slides for Java، لديك أداة قوية تحت تصرفك لإنشاء عروض تقديمية مذهلة برمجيًا. باتباع هذا الدليل التفصيلي، يمكنك بسهولة إضافة أشكال مملوءة بالتدرج إلى شرائحك، مما يجعل المحتوى الخاص بك أكثر جاذبية وجاذبية بصريًا.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint التقديمية ومعالجتها برمجيًا.
### هل يمكنني استخدام Aspose.Slides مجانًا؟
 يمكنك استخدام Aspose.Slides مع ملف[تجربة مجانية](https://releases.aspose.com/) لاختبار ميزاته قبل شراء الترخيص.
### ما هي توقفات التدرج؟
توقفات التدرج هي نقاط محددة داخل التدرج تحدد اللون وموضعه داخل التدرج.
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides؟
 للحصول على الدعم، قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### أين يمكنني تنزيل أحدث إصدار من Aspose.Slides لـ Java؟
 يمكنك تنزيل أحدث إصدار من[صفحة تنزيل Aspose.Slides](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
