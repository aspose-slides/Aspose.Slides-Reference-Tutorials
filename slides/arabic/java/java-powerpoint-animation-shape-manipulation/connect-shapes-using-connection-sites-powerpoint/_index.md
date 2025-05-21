---
"description": "تعلّم كيفية ربط الأشكال في PowerPoint باستخدام Aspose.Slides لجافا. أتمتة عروضك التقديمية بسهولة."
"linktitle": "ربط الأشكال باستخدام مواقع الاتصال في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ربط الأشكال باستخدام مواقع الاتصال في PowerPoint"
"url": "/ar/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ربط الأشكال باستخدام مواقع الاتصال في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية ربط الأشكال باستخدام مواقع الربط في PowerPoint باستخدام Aspose.Slides لجافا. تتيح لنا هذه المكتبة القوية التعامل برمجيًا مع عروض PowerPoint التقديمية، مما يجعل مهام مثل ربط الأشكال سلسة وفعالة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت جافا على نظامك. يمكنك تنزيلها وتثبيتها من [موقع إلكتروني](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من [صفحة التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): اختر بيئة التطوير المتكاملة لتطوير Java، مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.

## استيراد الحزم
للبدء، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;

```
## الخطوة 1: الوصول إلى مجموعة الأشكال
الوصول إلى مجموعة الأشكال للشريحة المحددة:
```java
// المسار إلى دليل المستندات.                    
String dataDir = "Your Document Directory";
// إنشاء فئة عرض تقديمي تمثل ملف PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## الخطوة 2: إضافة شكل الموصل
إضافة شكل موصل إلى مجموعة أشكال الشريحة:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## الخطوة 3: إضافة الأشكال التلقائية
أضف أشكالًا تلقائية مثل القطع الناقص والمستطيل:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## الخطوة 4: ربط الأشكال بالموصلات
ربط الأشكال بالموصل:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## الخطوة 5: إعداد فهرس موقع الاتصال
قم بتعيين مؤشر موقع الاتصال المطلوب للأشكال:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية ربط الأشكال باستخدام مواقع الربط في PowerPoint باستخدام Aspose.Slides لجافا. بفضل هذه المعرفة، يمكنك الآن أتمتة عروض PowerPoint التقديمية وتخصيصها بسهولة.
## الأسئلة الشائعة
### هل يمكن استخدام Aspose.Slides for Java لمهام معالجة PowerPoint الأخرى؟
نعم، يوفر Aspose.Slides for Java مجموعة واسعة من الوظائف لإنشاء وتحرير وتحويل عروض PowerPoint.
### هل استخدام Aspose.Slides لـ Java مجاني؟
Aspose.Slides لجافا هي مكتبة تجارية، ولكن يمكنك استكشاف ميزاتها من خلال نسخة تجريبية مجانية. تفضل بزيارة [هنا](https://releases.aspose.com/) للبدء.
### هل يمكنني الحصول على الدعم إذا واجهت أي مشاكل أثناء استخدام Aspose.Slides لـ Java؟
نعم، يمكنك الحصول على الدعم من منتديات مجتمع Aspose [هنا](https://forum.aspose.com/c/slides/11).
### هل تتوفر تراخيص مؤقتة لـ Aspose.Slides لـ Java؟
نعم، تتوفر تراخيص مؤقتة لأغراض الاختبار والتقييم. يمكنك الحصول على واحدة. [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء ترخيص لـ Aspose.Slides لـ Java؟
يمكنك شراء الترخيص من موقع Aspose [هنا](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}