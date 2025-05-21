---
"description": "تعرف على كيفية إنشاء قطع ناقص منسق في PowerPoint باستخدام Aspose.Slides لـ Java من خلال دليلنا المفصل خطوة بخطوة."
"linktitle": "إنشاء شكل بيضاوي منسق في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء شكل بيضاوي منسق في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء شكل بيضاوي منسق في PowerPoint

## مقدمة
مرحبًا بكم في هذا الدليل الشامل لإنشاء شكل بيضاوي منسق في PowerPoint باستخدام Aspose.Slides لجافا. Aspose.Slides مكتبة فعّالة تُمكّن المطورين من التعامل مع ملفات PowerPoint برمجيًا. سواءً كنت تُؤتمت إنشاء الشرائح أو تُحسّن عروضك التقديمية بأشكال مخصصة، سيُرشدك هذا الدليل خطوة بخطوة، مما يضمن لك إمكانية إضافة شكل بيضاوي منسق بدقة إلى شرائحك بسهولة. لنبدأ ونرى كيف يُمكننا تحقيق ذلك!
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK 1.6 أو أعلى.
2. Aspose.Slides لـ Java: قم بتنزيل الإصدار الأحدث من [Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse.
4. المعرفة الأساسية بلغة جافا: مطلوب معرفة ببرمجة جافا.
## استيراد الحزم
لبدء استخدام Aspose.Slides، عليك استيراد الحزم اللازمة. إليك كيفية القيام بذلك:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## الخطوة 1: إعداد دليل المشروع الخاص بك
أولاً، ستحتاج إلى دليل لتخزين ملفات PowerPoint الخاصة بك.
### إنشاء دليل
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
تأكد من استبدال `"Your Document Directory"` مع المسار الفعلي الذي تريد تخزين ملفاتك فيه.
## الخطوة 2: تهيئة العرض التقديمي
الآن، قم بإنشاء فئة العرض التقديمي، والتي تمثل ملف PowerPoint.
```java
// إنشاء فئة عرض تقديمي تمثل PPTX
Presentation pres = new Presentation();
```
## الخطوة 3: الحصول على الشريحة الأولى
بعد ذلك، احصل على الشريحة الأولى من العرض التقديمي حيث ستضيف القطع الناقص.
```java
// احصل على الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة شكل بيضاوي
أضف شكلًا تلقائيًا من نوع القطع الناقص إلى الشريحة.
```java
// إضافة شكل تلقائي من نوع القطع الناقص
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
هنا، `50, 150, 150, 50` هي إحداثيات وحجم القطع الناقص (موضع x، وموضع y، والعرض، والارتفاع).
## الخطوة 5: تطبيق التنسيق على القطع الناقص
الآن، طبّق بعض التنسيق على القطع الناقص. سنعيّن لون تعبئة ثابتًا ولون خط.
### تعيين لون التعبئة
```java
// تطبيق بعض التنسيق على شكل القطع الناقص
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### تعيين لون الخط وعرضه
```java
// تطبيق بعض التنسيق على خط Ellipse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## الخطوة 6: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي في الدليل المحدد.
```java
// اكتب ملف PPTX على القرص
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## الخطوة 7: التخلص من كائن العرض التقديمي
تخلص من كائن العرض لتحرير الموارد.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## خاتمة
تهانينا! لقد نجحت في إنشاء شكل بيضاوي منسق في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. شرح لك هذا البرنامج التعليمي خطوات إعداد مشروعك، وإضافة شكل بيضاوي، وتطبيق التنسيق، وحفظ العرض التقديمي. بفضل هذه المهارات، يمكنك الآن تحسين شرائح PowerPoint برمجيًا، مما يجعل عروضك التقديمية أكثر ديناميكية وجاذبية بصريًا.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint وتعديلها وإدارتها برمجيًا.
### هل يمكنني استخدام Aspose.Slides لـ Java مع أي IDE؟
نعم، يمكنك استخدام Aspose.Slides لـ Java مع أي Java IDE مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.
### هل أحتاج إلى ترخيص لـ Aspose.Slides؟
نعم، Aspose.Slides منتج تجاري، وتحتاج إلى ترخيص للاستفادة من جميع وظائفه. يمكنك الحصول على ترخيص مؤقت. [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
يمكنك العثور على وثائق مفصلة على Aspose.Slides لـ Java [صفحة التوثيق](https://reference.aspose.com/slides/java/).
### هل هناك دعم متاح لـ Aspose.Slides؟
نعم، تقدم Aspose الدعم من خلال [المنتدى](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}