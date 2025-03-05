---
title: استخدم ShapeUtil للأشكال الهندسية في PowerPoint
linktitle: استخدم ShapeUtil للأشكال الهندسية في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بإنشاء أشكال مخصصة في PowerPoint باستخدام Aspose.Slides لـ Java. اتبع هذا الدليل المفصّل خطوة بخطوة لتحسين عروضك التقديمية.
type: docs
weight: 23
url: /ar/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/
---
## مقدمة
غالبًا ما يتطلب إنشاء عروض PowerPoint التقديمية الجذابة أكثر من مجرد استخدام الأشكال والنصوص القياسية. تخيل أنك قادر على إضافة أشكال مخصصة ومسارات نصية مباشرة إلى شرائحك، مما يعزز التأثير البصري لعرضك التقديمي. باستخدام Aspose.Slides لـ Java، يمكنك تحقيق ذلك بسهولة. سيرشدك هذا البرنامج التعليمي خلال عملية استخدام`ShapeUtil` فئة لإنشاء الأشكال الهندسية في عروض PowerPoint التقديمية. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيساعدك هذا الدليل التفصيلي خطوة بخطوة على الاستفادة من قوة Aspose.Slides لـ Java لإنشاء محتوى مذهل ومخصص الشكل.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، هناك بعض الأشياء التي ستحتاج إليها:
1. Java Development Kit (JDK): تأكد من تثبيت JDK 8 أو أعلى على جهازك.
2.  Aspose.Slides لـ Java: قم بتنزيل أحدث إصدار من[صفحة التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير: استخدم أي Java IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans.
4.  الترخيص المؤقت: احصل على ترخيص مؤقت مجاني من[صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/) لفتح الوظائف الكاملة لـ Aspose.Slides لـ Java.
## حزم الاستيراد
للبدء، تحتاج إلى استيراد الحزم اللازمة للعمل مع Aspose.Slides وJava AWT (مجموعة أدوات النافذة المجردة):
```java
import com.aspose.slides.*;

import java.awt.*;
import java.awt.Shape;
import java.awt.font.GlyphVector;
import java.awt.image.BufferedImage;
```
## الخطوة 1: إعداد مشروعك
أولاً، قم بإعداد مشروع Java الخاص بك وأضف Aspose.Slides for Java إلى تبعيات مشروعك. يمكنك القيام بذلك عن طريق إضافة ملفات JAR مباشرةً أو باستخدام أداة إنشاء مثل Maven أو Gradle.
## الخطوة 2: إنشاء عرض تقديمي جديد
ابدأ بإنشاء كائن عرض تقديمي جديد في PowerPoint. سيكون هذا الكائن هو اللوحة القماشية التي ستضيف إليها الأشكال المخصصة.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة شكل مستطيل
بعد ذلك، قم بإضافة شكل مستطيل أساسي إلى الشريحة الأولى من العرض التقديمي. سيتم تعديل هذا الشكل لاحقًا ليشمل مسارًا هندسيًا مخصصًا.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## الخطوة 4: استرداد وتعديل المسار الهندسي
 استرجع المسار الهندسي للشكل المستطيل وقم بتعديل وضع التعبئة الخاص به إلى`None`. تعتبر هذه الخطوة حاسمة لأنها تسمح لك بدمج هذا المسار مع مسار هندسي مخصص آخر.
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## الخطوة 5: إنشاء مسار هندسي مخصص من النص
الآن، قم بإنشاء مسار هندسي مخصص بناءً على النص. يتضمن ذلك تحويل سلسلة نصية إلى مسار رسومي ثم تحويل هذا المسار إلى مسار هندسي.
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## الخطوة 6: الجمع بين المسارات الهندسية
قم بدمج المسار الهندسي الأصلي مع المسار الهندسي الجديد القائم على النص وقم بتعيين هذا المزيج على الشكل.
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## الخطوة 7: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل في ملف. سيؤدي هذا إلى إخراج ملف PowerPoint بالأشكال المخصصة الخاصة بك.
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## خاتمة
تهانينا! لقد قمت للتو بإنشاء شكل هندسي مخصص في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يرشدك هذا البرنامج التعليمي خلال كل خطوة، بدءًا من إعداد مشروعك ووصولاً إلى إنشاء المسارات الهندسية ودمجها. ومن خلال إتقان هذه التقنيات، يمكنك إضافة عناصر فريدة وملفتة للنظر إلى عروضك التقديمية، مما يجعلها مميزة.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية للعمل مع ملفات PowerPoint في Java. يسمح لك بإنشاء العروض التقديمية وتعديلها وتحويلها برمجياً.
### كيف أقوم بتثبيت Aspose.Slides لـ Java؟
 يمكنك تنزيل أحدث إصدار من[صفحة التحميل](https://releases.aspose.com/slides/java/) وأضف ملفات JAR إلى مشروعك.
### هل يمكنني استخدام Aspose.Slides مجانًا؟
يقدم Aspose.Slides إصدارًا تجريبيًا مجانيًا، يمكنك تنزيله من خلاله[هنا](https://releases.aspose.com/)للحصول على الوظائف الكاملة، تحتاج إلى شراء ترخيص.
### ما هو استخدام فئة ShapeUtil؟
 ال`ShapeUtil` توفر الفئة في Aspose.Slides أساليب مفيدة للعمل مع الأشكال، مثل تحويل المسارات الرسومية إلى مسارات هندسية.
### أين يمكنني الحصول على الدعم لـ Aspose.Slides؟
 يمكنك الحصول على الدعم من[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).