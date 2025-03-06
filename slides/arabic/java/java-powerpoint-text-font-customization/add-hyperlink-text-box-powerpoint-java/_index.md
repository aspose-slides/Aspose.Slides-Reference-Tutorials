---
title: إضافة ارتباط تشعبي إلى مربع النص في PowerPoint باستخدام Java
linktitle: إضافة ارتباط تشعبي إلى مربع النص في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة ارتباطات تشعبية إلى مربعات نص PowerPoint باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع أمثلة لمطوري Java.
weight: 23
url: /ar/java/java-powerpoint-text-font-customization/add-hyperlink-text-box-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة ارتباط تشعبي إلى مربع النص في PowerPoint باستخدام Java

## مقدمة
في العصر الرقمي الحالي، يعد إنشاء عروض تقديمية ديناميكية تشاركية ومفيدة أمرًا بالغ الأهمية للتواصل الفعال. غالبًا ما يلجأ مطورو Java الذين يسعون إلى تحسين تطبيقاتهم بميزات تفاعلية إلى Aspose.Slides for Java، وهي مكتبة قوية تتيح معالجة عروض PowerPoint التقديمية برمجيًا. يتعمق هذا البرنامج التعليمي في إحدى هذه الميزات: إضافة ارتباطات تشعبية إلى مربعات النص في عروض PowerPoint التقديمية باستخدام Java. بحلول نهاية هذا الدليل، سيكون لديك فهم واضح لكيفية تنفيذ هذه الوظيفة بسلاسة في تطبيقات Java الخاصة بك.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة جافا.
- JDK (Java Development Kit) مثبت على نظامك.
-  تم تنزيل وإعداد Aspose.Slides لمكتبة Java. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- تم تثبيت بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## حزم الاستيراد
قبل الغوص في المثال، تأكد من استيراد الحزم اللازمة:
```java
import com.aspose.slides.*;
import java.io.File;
```
## الخطوة 1: إنشاء كائن العرض التقديمي
أولاً، قم بإنشاء كائن عرض تقديمي يمثل عرض تقديمي لـ PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation pptxPresentation = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة وتعديلها
احصل على الشريحة الأولى من العرض التقديمي لمعالجتها.
```java
ISlide slide = pptxPresentation.getSlides().get_Item(0);
```
## الخطوة 3: إضافة شكل تلقائي (مربع نص)
قم بإضافة شكل تلقائي من النوع المستطيل إلى الشريحة عند الإحداثيات المحددة.
```java
IShape pptxShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 150, 50);
```
## الخطوة 4: الوصول إلى إطار النص
تحويل الشكل إلى شكل تلقائي والوصول إلى إطار النص الخاص به.
```java
IAutoShape pptxAutoShape = (IAutoShape) pptxShape;
pptxAutoShape.addTextFrame("");
ITextFrame textFrame = pptxAutoShape.getTextFrame();
```
## الخطوة 5: إضافة نص إلى إطار النص
أضف محتوى النص المطلوب إلى إطار النص.
```java
textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0).setText("Aspose.Slides");
```
## الخطوة 6: تعيين الارتباط التشعبي للنص
قم بتعيين ارتباط تشعبي لجزء النص المضاف في الخطوة السابقة.
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
IHyperlinkManager hyperlinkManager = portion.getPortionFormat().getHyperlinkManager();
hyperlinkManager.setExternalHyperlinkClick("http://www.aspose.com");
```
## الخطوة 7: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل في موقع محدد.
```java
pptxPresentation.save(dataDir + "hLinkPPTX_out.pptx", SaveFormat.Pptx);
```

## خاتمة
باتباع هذه الخطوات، تكون قد تعلمت بنجاح كيفية إضافة ارتباطات تشعبية إلى مربعات النص في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java. تتيح لك هذه الإمكانية إنشاء محتوى ديناميكي وتفاعلي داخل تطبيقات Java لديك، مما يعزز تفاعل المستخدم وتفاعله.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مجانًا؟
 نعم، يمكنك البدء بالإصدار التجريبي المجاني المتاح[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
 الوثائق التفصيلية متاحة[هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم إذا واجهت مشاكل؟
 يمكنك الحصول على الدعم من مجتمع Aspose[هنا](https://forum.aspose.com/c/slides/11).
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ Java؟
 نعم، التراخيص المؤقتة متاحة للشراء[هنا](https://purchase.aspose.com/temporary-license/).
### هل Aspose.Slides متوافق مع مكتبات Java الأخرى؟
يتكامل Aspose.Slides بشكل جيد مع مكتبات Java المتنوعة لمعالجة PowerPoint بشكل شامل.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
