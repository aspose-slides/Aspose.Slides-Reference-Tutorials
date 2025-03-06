---
title: إنشاء القطع الناقص المنسق في PowerPoint
linktitle: إنشاء القطع الناقص المنسق في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء شكل بيضاوي منسق في PowerPoint باستخدام Aspose.Slides لـ Java من خلال دليلنا التفصيلي خطوة بخطوة.
weight: 17
url: /ar/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
مرحبًا بك في هذا البرنامج التعليمي الشامل حول إنشاء شكل بيضاوي منسق في PowerPoint باستخدام Aspose.Slides لـ Java. Aspose.Slides هي مكتبة قوية تسمح للمطورين بمعالجة ملفات PowerPoint برمجياً. سواء كنت تقوم بأتمتة إنشاء الشرائح أو تحسين العروض التقديمية باستخدام أشكال مخصصة، سيرشدك هذا الدليل خلال كل خطوة، مما يضمن أنه يمكنك إضافة شكل بيضاوي منسق بشكل مثالي إلى شرائحك بسهولة. دعونا نتعمق ونرى كيف يمكننا تحقيق ذلك!
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK 1.6 أو أعلى.
2.  Aspose.Slides لـ Java: قم بتنزيل أحدث إصدار من[Aspose.Slides لجافا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse.
4. المعرفة الأساسية بـ Java: الإلمام ببرمجة Java مطلوب.
## حزم الاستيراد
لبدء استخدام Aspose.Slides، تحتاج إلى استيراد الحزم الضرورية. وإليك كيف يمكنك القيام بذلك:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## الخطوة 1: قم بإعداد دليل المشروع الخاص بك
أولاً، أنت بحاجة إلى دليل لتخزين ملفات PowerPoint الخاصة بك.
### إنشاء دليل
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 تأكد من استبدال`"Your Document Directory"` بالمسار الفعلي الذي تريد تخزين ملفاتك فيه.
## الخطوة 2: تهيئة العرض التقديمي
الآن، قم بإنشاء مثيل لفئة العرض التقديمي، التي تمثل ملف PowerPoint.
```java
// إنشاء فئة العرض التقديمي التي تمثل PPTX
Presentation pres = new Presentation();
```
## الخطوة 3: احصل على الشريحة الأولى
بعد ذلك، احصل على الشريحة الأولى من العرض التقديمي حيث ستضيف الشكل الناقص.
```java
// احصل على الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة شكل القطع الناقص
أضف شكلاً تلقائيًا من نوع القطع الناقص إلى الشريحة.
```java
// إضافة شكل تلقائي لنوع القطع الناقص
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 هنا،`50, 150, 150, 50` هي إحداثيات وحجم القطع الناقص (موضع x، موضع y، العرض، الارتفاع).
## الخطوة 5: تطبيق التنسيق على القطع الناقص
الآن، قم بتطبيق بعض التنسيق على الشكل الناقص. سنقوم بتعيين لون تعبئة خالص ولون خط.
### تعيين لون التعبئة
```java
// تطبيق بعض التنسيق على شكل القطع الناقص
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### ضبط لون الخط وعرضه
```java
// قم بتطبيق بعض التنسيق على خط Ellipse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## الخطوة 6: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي في الدليل المحدد لديك.
```java
// اكتب ملف PPTX على القرص
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## الخطوة 7: التخلص من كائن العرض التقديمي
تخلص من كائن العرض التقديمي لتحرير الموارد.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## خاتمة
تهانينا! لقد نجحت في إنشاء شكل بيضاوي منسق في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يرشدك هذا البرنامج التعليمي خلال إعداد مشروعك وإضافة شكل بيضاوي وتطبيق التنسيق وحفظ العرض التقديمي. باستخدام هذه المهارات، يمكنك الآن تحسين شرائح PowerPoint الخاصة بك برمجيًا، مما يجعل عروضك التقديمية أكثر ديناميكية وجاذبية بصريًا.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية وتعديلها وإدارتها برمجياً.
### هل يمكنني استخدام Aspose.Slides لـ Java مع أي بيئة تطوير متكاملة (IDE)؟
نعم، يمكنك استخدام Aspose.Slides لـ Java مع أي Java IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans.
### هل أحتاج إلى ترخيص لـ Aspose.Slides؟
نعم، Aspose.Slides هو منتج تجاري، وتحتاج إلى ترخيص للحصول على الوظائف الكاملة. يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
 يمكنك العثور على وثائق مفصلة على Aspose.Slides لـ Java[صفحة التوثيق](https://reference.aspose.com/slides/java/).
### هل هناك دعم متاح لـ Aspose.Slides؟
 نعم، Aspose يقدم الدعم من خلال[المنتدى](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
