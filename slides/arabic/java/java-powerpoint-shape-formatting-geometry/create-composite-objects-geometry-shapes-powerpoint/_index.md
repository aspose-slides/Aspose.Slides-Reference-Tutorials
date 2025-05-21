---
"description": "تعلّم كيفية إنشاء كائنات مركّبة بأشكال هندسية باستخدام Aspose.Slides لجافا من خلال هذا البرنامج التعليمي الشامل. مثالي لمطوّري جافا."
"linktitle": "إنشاء كائنات مركبة في أشكال هندسية"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء كائنات مركبة في أشكال هندسية"
"url": "/ar/java/java-powerpoint-shape-formatting-geometry/create-composite-objects-geometry-shapes-powerpoint/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء كائنات مركبة في أشكال هندسية

## مقدمة
أهلاً! هل رغبتَ يومًا في إنشاء أشكالٍ مذهلة ومعقدة في عروض PowerPoint التقديمية باستخدام جافا؟ حسنًا، أنت في المكان المناسب. في هذا البرنامج التعليمي، سنتعمق في مكتبة Aspose.Slides القوية لجافا لإنشاء كائنات مركبة بأشكال هندسية. سواءً كنتَ مطورًا محترفًا أو مبتدئًا، سيساعدك هذا الدليل التفصيلي على تحقيق نتائج مبهرة في وقت قصير. هل أنت مستعد للبدء؟ هيا بنا!
## المتطلبات الأساسية
قبل أن ننتقل إلى الكود، هناك بعض الأشياء التي ستحتاجها:
- مجموعة تطوير Java (JDK): تأكد من تثبيت JDK 1.8 أو أعلى على جهازك.
- بيئة التطوير المتكاملة (IDE): بيئة التطوير المتكاملة مثل IntelliJ IDEA أو Eclipse سوف تجعل حياتك أسهل.
- Aspose.Slides لـ Java: يمكنك تنزيله من [هنا](https://releases.aspose.com/slides/java/) أو استخدم Maven لتضمينه في مشروعك.
- المعرفة الأساسية بلغة Java: يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا بلغة Java.
## استيراد الحزم
أولاً وقبل كل شيء، دعنا نستورد الحزم اللازمة للبدء في استخدام Aspose.Slides لـ Java.
```java
import com.aspose.slides.*;

```

قد يبدو إنشاء كائنات مركبة أمرًا معقدًا، ولكن بتقسيمه إلى خطوات سهلة، ستجد أنه أسهل مما تظن. سننشئ عرضًا تقديميًا على PowerPoint، ونضيف شكلًا، ثم نحدد ونطبق مسارات هندسية متعددة لتكوين شكل مركب.
## الخطوة 1: إعداد مشروعك
قبل كتابة أي شيفرة برمجية، قم بإعداد مشروع جافا. أنشئ مشروعًا جديدًا في بيئة التطوير المتكاملة (IDE) لديك، وأدرج فيه مكتبة Aspose.Slides لجافا. يمكنك إضافة المكتبة باستخدام Maven أو تنزيل ملف JAR من [صفحة تنزيل Aspose.Slides](https://releases.aspose.com/slides/java/).
### إضافة Aspose.Slides إلى مشروعك باستخدام Maven
إذا كنت تستخدم Maven، فأضف التبعية التالية إلى ملفك `pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace with the latest version -->
</dependency>
```
## الخطوة 2: تهيئة العرض التقديمي
الآن، لنُنشئ عرضًا تقديميًا جديدًا على PowerPoint. سنبدأ بتهيئة `Presentation` فصل.
```java
// اسم ملف الإخراج
String resultPath = "Your Output Directory" +  "GeometryShapeCompositeObjects.pptx";
Presentation pres = new Presentation();
```
## الخطوة 3: إنشاء شكل جديد
بعد ذلك، سنضيف شكل مستطيل جديد إلى الشريحة الأولى من عرضنا التقديمي.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## الخطوة 4: تحديد مسار الهندسة الأول
سنقوم بتحديد الجزء الأول من الشكل المركب لدينا عن طريق إنشاء `GeometryPath` وإضافة نقاط إليها.
```java
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.moveTo(0, 0);
geometryPath0.lineTo(shape.getWidth(), 0);
geometryPath0.lineTo(shape.getWidth(), shape.getHeight() / 3);
geometryPath0.lineTo(0, shape.getHeight() / 3);
geometryPath0.closeFigure();
```
## الخطوة 5: تحديد مسار الهندسة الثاني
وبالمثل، قم بتحديد الجزء الثاني من الشكل المركب لدينا.
```java
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.moveTo(0, shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight());
geometryPath1.lineTo(0, shape.getHeight());
geometryPath1.closeFigure();
```
## الخطوة 6: دمج مسارات الهندسة
قم بدمج مساري الهندسة وضبطهما على الشكل.
```java
shape.setGeometryPaths(new GeometryPath[]{geometryPath0, geometryPath1});
```
## الخطوة 7: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الخاص بك في ملف.
```java
String resultPath = "Your Output Directory" + "GeometryShapeCompositeObjects.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## الخطوة 8: تنظيف الموارد
تأكد من إصدار أي موارد يستخدمها العرض التقديمي.
```java
if (pres != null) pres.dispose();
```
## خاتمة
وها أنت ذا! لقد نجحت في إنشاء شكل مُركّب باستخدام Aspose.Slides لجافا. بتقسيم العملية إلى خطوات بسيطة، يمكنك بسهولة إنشاء أشكال مُعقّدة وتحسين عروضك التقديمية. استمر في تجربة مسارات هندسية مُختلفة لإنشاء تصاميم فريدة.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة قوية لإنشاء عروض PowerPoint ومعالجتها وتحويلها في Java.
### كيف أقوم بتثبيت Aspose.Slides لـ Java؟
يمكنك تثبيته باستخدام Maven أو تنزيل ملف JAR من [موقع إلكتروني](https://releases.aspose.com/slides/java/).
### هل يمكنني استخدام Aspose.Slides لـ Java في المشاريع التجارية؟
نعم، ولكن ستحتاج إلى شراء ترخيص. يمكنك العثور على مزيد من التفاصيل على [صفحة الشراء](https://purchase.aspose.com/buy).
### هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على مزيد من الوثائق والدعم؟
تحقق من [التوثيق](https://reference.aspose.com/slides/java/) و [منتدى الدعم](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}