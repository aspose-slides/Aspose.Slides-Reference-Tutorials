---
title: ربط الأشكال باستخدام الموصلات في PowerPoint
linktitle: ربط الأشكال باستخدام الموصلات في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية ربط الأشكال باستخدام الموصلات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. تعليمي خطوة بخطوة للمبتدئين.
weight: 18
url: /ar/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية ربط الأشكال باستخدام الموصلات في عروض PowerPoint التقديمية بمساعدة Aspose.Slides for Java. اتبع هذه الإرشادات خطوة بخطوة لربط الأشكال بكفاءة وإنشاء شرائح جذابة بصريًا.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  تم تنزيل Aspose.Slides لـ Java وإعداده. إذا لم تكن قد قمت بتثبيته بعد، يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- محرر أكواد برمجية مثل Eclipse أو IntelliJ IDEA.

## حزم الاستيراد
أولاً، قم باستيراد الحزم اللازمة للعمل مع Aspose.Slides في مشروع Java الخاص بك.
```java
import com.aspose.slides.*;

```
## الخطوة 1: إنشاء مثيل لفئة العرض التقديمي
 إنشاء مثيل`Presentation`class الذي يمثل ملف PPTX الذي تعمل عليه.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## الخطوة 2: الوصول إلى مجموعة الأشكال
قم بالوصول إلى مجموعة الأشكال الخاصة بالشريحة المحددة حيث تريد إضافة الأشكال والموصلات.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## الخطوة 3: إضافة الأشكال
أضف الأشكال المطلوبة إلى الشريحة. في هذا المثال، سنقوم بإضافة القطع الناقص والمستطيل.
```java
// إضافة الشكل التلقائي للقطع الناقص
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// إضافة مستطيل الشكل التلقائي
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## الخطوة 4: إضافة الموصل
أضف شكل موصل إلى مجموعة أشكال الشرائح.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## الخطوة 5: ضم الأشكال إلى الموصلات
قم بتوصيل الأشكال بالموصل.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## الخطوة 6: إعادة توجيه الرابط
استدعاء إعادة التوجيه لتعيين أقصر مسار تلقائي بين الأشكال.
```java
connector.reroute();
```
## الخطوة 7: حفظ العرض التقديمي
احفظ العرض التقديمي بعد توصيل الأشكال باستخدام الموصلات.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
وأخيرًا، لا تنس التخلص من كائن العرض التقديمي.
```java
if (input != null) input.dispose();
```
لقد نجحت الآن في توصيل الأشكال باستخدام الموصلات في PowerPoint باستخدام Aspose.Slides لـ Java.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية ربط الأشكال باستخدام الموصلات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. باتباع هذه الخطوات البسيطة، يمكنك تحسين عروضك التقديمية باستخدام رسوم بيانية ومخططات انسيابية جذابة بصريًا.
## الأسئلة الشائعة
### هل يمكنني تخصيص مظهر الموصلات في Aspose.Slides لـ Java؟
نعم، يمكنك تخصيص خصائص مختلفة للموصلات مثل اللون ونمط الخط والسمك لتناسب احتياجات العرض التقديمي الخاص بك.
### هل Aspose.Slides for Java متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides for Java تنسيقات PowerPoint المتنوعة، بما في ذلك PPTX وPPT وODP.
### هل يمكنني ربط أكثر من شكلين بموصل واحد؟
نعم، يمكنك توصيل أشكال متعددة باستخدام موصلات معقدة توفرها Aspose.Slides لـ Java.
### هل يقدم Aspose.Slides for Java الدعم لإضافة نص إلى الأشكال؟
بالتأكيد، يمكنك بسهولة إضافة نص إلى الأشكال والموصلات برمجيًا باستخدام Aspose.Slides لـ Java.
### هل يوجد منتدى مجتمعي أو قناة دعم متاحة لـ Aspose.Slides لمستخدمي Java؟
 نعم، يمكنك العثور على موارد مفيدة وطرح الأسئلة والتفاعل مع مستخدمين آخرين في منتدى Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
