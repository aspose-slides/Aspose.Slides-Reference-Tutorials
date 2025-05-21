---
"description": "أنشئ أشكالًا مخصصة في PowerPoint باستخدام Aspose.Slides لجافا. اتبع هذا الدليل خطوة بخطوة لتحسين عروضك التقديمية."
"linktitle": "استخدم ShapeUtil للشكل الهندسي في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "استخدم ShapeUtil للشكل الهندسي في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# استخدم ShapeUtil للشكل الهندسي في PowerPoint

## مقدمة
غالبًا ما يتطلب إنشاء عروض PowerPoint جذابة بصريًا أكثر من مجرد استخدام الأشكال والنصوص القياسية. تخيل إمكانية إضافة أشكال ومسارات نصية مخصصة مباشرةً إلى شرائحك، مما يعزز التأثير البصري لعرضك التقديمي. باستخدام Aspose.Slides لجافا، يمكنك تحقيق ذلك بسهولة. سيرشدك هذا البرنامج التعليمي خلال عملية استخدام `ShapeUtil` فئة لإنشاء أشكال هندسية في عروض PowerPoint التقديمية. سواء كنت مطورًا محترفًا أو مبتدئًا، سيساعدك هذا الدليل التفصيلي على الاستفادة من قوة Aspose.Slides لـ Java لإنشاء محتوى مذهل بأشكال مخصصة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، هناك بعض الأشياء التي ستحتاجها:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK 8 أو أعلى على جهازك.
2. Aspose.Slides لـ Java: قم بتنزيل أحدث إصدار من [صفحة التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير: استخدم أي بيئة تطوير متكاملة لـ Java مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.
4. رخصة مؤقتة: احصل على رخصة مؤقتة مجانية من [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/) لفتح قفل الوظائف الكاملة لـ Aspose.Slides لـ Java.
## استيراد الحزم
للبدء، تحتاج إلى استيراد الحزم اللازمة للعمل مع Aspose.Slides وJava AWT (Abstract Window Toolkit):
```java
import com.aspose.slides.*;

import java.awt.*;
import java.awt.Shape;
import java.awt.font.GlyphVector;
import java.awt.image.BufferedImage;
```
## الخطوة 1: إعداد مشروعك
أولاً، قم بإعداد مشروع جافا الخاص بك وأضف Aspose.Slides for Java إلى تبعيات مشروعك. يمكنك القيام بذلك بإضافة ملفات JAR مباشرةً أو باستخدام أداة بناء مثل Maven أو Gradle.
## الخطوة 2: إنشاء عرض تقديمي جديد
ابدأ بإنشاء كائن عرض تقديمي جديد في PowerPoint. سيكون هذا الكائن بمثابة لوحة الرسم التي ستضيف إليها أشكالك المخصصة.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة شكل مستطيل
بعد ذلك، أضف شكل مستطيل أساسي إلى الشريحة الأولى من العرض التقديمي. سيتم تعديل هذا الشكل لاحقًا ليشمل مسارًا هندسيًا مخصصًا.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## الخطوة 4: استرداد مسار الهندسة وتعديله
استرداد مسار هندسة شكل المستطيل وتعديل وضع التعبئة الخاص به إلى `None`. هذه الخطوة مهمة لأنها تسمح لك بدمج هذا المسار مع مسار هندسي مخصص آخر.
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## الخطوة 5: إنشاء مسار هندسي مخصص من النص
الآن، أنشئ مسارًا هندسيًا مخصصًا بناءً على نص. يتضمن ذلك تحويل سلسلة نصية إلى مسار رسومي، ثم تحويل هذا المسار إلى مسار هندسي.
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## الخطوة 6: دمج مسارات الهندسة
قم بدمج مسار الهندسة الأصلي مع مسار الهندسة الجديد المستند إلى النص ثم قم بضبط هذا المزيج على الشكل.
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## الخطوة 7: حفظ العرض التقديمي
أخيرًا، احفظ العرض التقديمي المُعدَّل في ملف. سيؤدي هذا إلى إخراج ملف PowerPoint بأشكالك المُخصَّصة.
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## خاتمة
تهانينا! لقد أنشأتَ للتو شكلًا هندسيًا مخصصًا في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. شرح لك هذا البرنامج التعليمي كل خطوة، بدءًا من إعداد مشروعك وحتى إنشاء مسارات هندسية ودمجها. بإتقان هذه التقنيات، يمكنك إضافة عناصر فريدة وملفتة للنظر إلى عروضك التقديمية، مما يجعلها مميزة.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي واجهة برمجة تطبيقات فعّالة للعمل مع ملفات PowerPoint بلغة Java. تتيح لك إنشاء العروض التقديمية وتعديلها وتحويلها برمجيًا.
### كيف أقوم بتثبيت Aspose.Slides لـ Java؟
يمكنك تنزيل الإصدار الأحدث من [صفحة التحميل](https://releases.aspose.com/slides/java/) وأضف ملفات JAR إلى مشروعك.
### هل يمكنني استخدام Aspose.Slides مجانًا؟
يقدم Aspose.Slides إصدارًا تجريبيًا مجانيًا، يمكنك تنزيله من [هنا](https://releases.aspose.com/)للحصول على الوظائف الكاملة، تحتاج إلى شراء ترخيص.
### ما هو استخدام فئة ShapeUtil؟
ال `ShapeUtil` توفر الفئة في Aspose.Slides طرقًا مساعدة للعمل مع الأشكال، مثل تحويل المسارات الرسومية إلى مسارات هندسية.
### أين يمكنني الحصول على الدعم لـ Aspose.Slides؟
يمكنك الحصول على الدعم من [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}