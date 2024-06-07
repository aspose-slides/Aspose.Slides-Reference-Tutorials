---
title: ربط الأشكال باستخدام مواقع الاتصال في PowerPoint
linktitle: ربط الأشكال باستخدام مواقع الاتصال في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية ربط الأشكال في PowerPoint باستخدام Aspose.Slides لـ Java. أتمتة العروض التقديمية الخاصة بك دون عناء.
type: docs
weight: 19
url: /ar/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية ربط الأشكال باستخدام مواقع الاتصال في PowerPoint باستخدام Aspose.Slides for Java. تسمح لنا هذه المكتبة القوية بمعالجة عروض PowerPoint التقديمية برمجياً، مما يجعل المهام مثل ربط الأشكال سلسة وفعالة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  Java Development Kit (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيله وتثبيته من[موقع إلكتروني](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من[صفحة التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): اختر بيئة تطوير متكاملة لتطوير Java، مثل IntelliJ IDEA أو Eclipse أو NetBeans.

## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## الخطوة 1: الوصول إلى مجموعة الأشكال
الوصول إلى مجموعة الأشكال للشريحة المحددة:
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة العرض التقديمي التي تمثل ملف PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## الخطوة 2: إضافة شكل الموصل
إضافة شكل موصل إلى مجموعة أشكال الشرائح:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## الخطوة 3: إضافة الأشكال التلقائية
إضافة أشكال تلقائية مثل القطع الناقص والمستطيل:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## الخطوة 4: ربط الأشكال بالموصلات
ضم الأشكال إلى الموصل:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## الخطوة 5: إعداد فهرس موقع الاتصال
قم بتعيين فهرس موقع الاتصال المطلوب للأشكال:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية ربط الأشكال باستخدام مواقع الاتصال في PowerPoint باستخدام Aspose.Slides for Java. بفضل هذه المعرفة، يمكنك الآن أتمتة عروض PowerPoint التقديمية وتخصيصها بسهولة.
## الأسئلة الشائعة
### هل يمكن استخدام Aspose.Slides for Java في مهام معالجة PowerPoint الأخرى؟
نعم، يوفر Aspose.Slides for Java مجموعة واسعة من الوظائف لإنشاء عروض PowerPoint التقديمية وتحريرها وتحويلها.
### هل Aspose.Slides لـ Java مجاني للاستخدام؟
 Aspose.Slides for Java هي مكتبة تجارية، ولكن يمكنك استكشاف ميزاتها من خلال نسخة تجريبية مجانية. يزور[هنا](https://releases.aspose.com/) للبدء.
### هل يمكنني الحصول على الدعم إذا واجهت أية مشكلات أثناء استخدام Aspose.Slides لـ Java؟
 نعم، يمكنك الحصول على الدعم من منتديات مجتمع Aspose[هنا](https://forum.aspose.com/c/slides/11).
### هل التراخيص المؤقتة متاحة لـ Aspose.Slides لـ Java؟
 نعم، التراخيص المؤقتة متاحة لأغراض الاختبار والتقييم. يمكنك الحصول على واحدة[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء ترخيص Aspose.Slides لـ Java؟
يمكنك شراء ترخيص من موقع Aspose[هنا](https://purchase.aspose.com/buy).