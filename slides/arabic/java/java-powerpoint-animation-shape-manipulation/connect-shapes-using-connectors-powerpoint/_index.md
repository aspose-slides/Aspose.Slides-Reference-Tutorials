---
"description": "تعلّم كيفية ربط الأشكال باستخدام الموصلات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة للمبتدئين."
"linktitle": "ربط الأشكال باستخدام الموصلات في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ربط الأشكال باستخدام الموصلات في PowerPoint"
"url": "/ar/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ربط الأشكال باستخدام الموصلات في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية ربط الأشكال باستخدام الموصلات في عروض PowerPoint التقديمية بمساعدة Aspose.Slides لجافا. اتبع هذه التعليمات خطوة بخطوة لربط الأشكال بكفاءة وإنشاء شرائح جذابة بصريًا.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على نظامك.
- تم تنزيل Aspose.Slides لجافا وإعداده. إذا لم تقم بتثبيته بعد، يمكنك تنزيله من [هنا](https://releases.aspose.com/slides/java/).
- محرر أكواد مثل Eclipse أو IntelliJ IDEA.

## استيراد الحزم
أولاً، قم باستيراد الحزم اللازمة للعمل مع Aspose.Slides في مشروع Java الخاص بك.
```java
import com.aspose.slides.*;

```
## الخطوة 1: إنشاء فئة العرض التقديمي
إنشاء مثيل `Presentation` الفئة التي تمثل ملف PPTX الذي تعمل عليه.
```java
// المسار إلى دليل المستندات.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## الخطوة 2: الوصول إلى مجموعة الأشكال
قم بالوصول إلى مجموعة الأشكال الخاصة بالشريحة المحددة التي تريد إضافة الأشكال والموصلات إليها.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## الخطوة 3: إضافة الأشكال
أضف الأشكال المطلوبة إلى الشريحة. في هذا المثال، سنضيف شكلًا بيضاويًا ومستطيلًا.
```java
// إضافة شكل بيضاوي تلقائي
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// إضافة شكل مستطيل تلقائي
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## الخطوة 4: إضافة موصل
أضف شكل موصل إلى مجموعة أشكال الشريحة.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## الخطوة 5: ربط الأشكال بالموصلات
قم بتوصيل الأشكال بالموصل.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## الخطوة 6: إعادة توجيه الموصل
قم بإعادة توجيه المكالمة لتعيين أقصر مسار تلقائي بين الأشكال.
```java
connector.reroute();
```
## الخطوة 7: حفظ العرض التقديمي
احفظ العرض التقديمي بعد توصيل الأشكال باستخدام الموصلات.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
وأخيرًا، لا تنسَ التخلص من كائن العرض التقديمي.
```java
if (input != null) input.dispose();
```
لقد قمت الآن بتوصيل الأشكال بنجاح باستخدام الموصلات في PowerPoint باستخدام Aspose.Slides for Java.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية ربط الأشكال باستخدام الموصلات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. باتباع هذه الخطوات البسيطة، يمكنك تحسين عروضك التقديمية بمخططات ومخططات انسيابية جذابة بصريًا.
## الأسئلة الشائعة
### هل يمكنني تخصيص مظهر الموصلات في Aspose.Slides لـ Java؟
نعم، يمكنك تخصيص خصائص مختلفة للموصلات مثل اللون ونمط الخط والسمك لتناسب احتياجات العرض التقديمي الخاص بك.
### هل Aspose.Slides for Java متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides for Java تنسيقات PowerPoint المختلفة، بما في ذلك PPTX، وPPT، وODP.
### هل يمكنني ربط أكثر من شكلين بموصل واحد؟
نعم، يمكنك ربط أشكال متعددة باستخدام موصلات معقدة يوفرها Aspose.Slides لـ Java.
### هل يوفر Aspose.Slides for Java الدعم لإضافة نص إلى الأشكال؟
بالتأكيد، يمكنك بسهولة إضافة نص إلى الأشكال والموصلات برمجيًا باستخدام Aspose.Slides لـ Java.
### هل يوجد منتدى مجتمعي أو قناة دعم متاحة لمستخدمي Aspose.Slides لـ Java؟
نعم، يمكنك العثور على موارد مفيدة وطرح الأسئلة والتفاعل مع مستخدمين آخرين على منتدى Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}