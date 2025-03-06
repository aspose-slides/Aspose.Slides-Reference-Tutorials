---
title: إضافة عقدة مساعد إلى SmartArt في Java PowerPoint
linktitle: إضافة عقدة مساعد إلى SmartArt في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة عقدة مساعدة إلى SmartArt في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides. تعزيز مهارات تحرير PowerPoint الخاص بك.
weight: 17
url: /ar/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة عقدة مساعدة إلى SmartArt في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيل وتثبيت أحدث إصدار من JDK من[هنا](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: قم بتنزيل وتثبيت مكتبة Aspose.Slides for Java من[هذا الرابط](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية في كود Java الخاص بك:
```java
import com.aspose.slides.*;
```
## الخطوة 1: إعداد العرض التقديمي
ابدأ بإنشاء مثيل عرض تقديمي باستخدام المسار إلى ملف PowerPoint الخاص بك:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## الخطوة 2: اجتياز الأشكال
قم بالتنقل عبر كل شكل داخل الشريحة الأولى من العرض التقديمي:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## الخطوة 3: التحقق من أشكال SmartArt
تحقق مما إذا كان الشكل من نوع SmartArt:
```java
if (shape instanceof ISmartArt)
```
## الخطوة 4: اجتياز عقد SmartArt
اجتياز كافة العقد في شكل SmartArt:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## الخطوة 5: التحقق من وجود عقدة المساعد
تحقق مما إذا كانت العقدة هي عقدة مساعدة:
```java
if (node.isAssistant())
```
## الخطوة 6: اضبط عقدة المساعد على الوضع العادي
إذا كانت العقدة عقدة مساعدة، فاضبطها على عقدة عادية:
```java
node.setAssistant(false);
```
## الخطوة 7: حفظ العرض التقديمي
حفظ العرض التقديمي المعدل:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## خاتمة
تهانينا! لقد نجحت في إضافة عقدة مساعدة إلى SmartArt في عرض Java PowerPoint التقديمي باستخدام Aspose.Slides.

## الأسئلة الشائعة
### هل يمكنني إضافة عقد مساعدة متعددة إلى SmartArt في العرض التقديمي؟
نعم، يمكنك إضافة عدة عقد مساعدة عن طريق تكرار العملية لكل عقدة.
### هل يعمل هذا البرنامج التعليمي لكل من قوالب PowerPoint وPowerPoint؟
نعم، يمكنك تطبيق هذا البرنامج التعليمي على كل من عروض PowerPoint التقديمية والقوالب.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides إصدارات PowerPoint من 97-2003 إلى الإصدار الأحدث.
### هل يمكنني تخصيص مظهر العقدة المساعدة؟
نعم، يمكنك تخصيص المظهر باستخدام الخصائص والأساليب المختلفة التي يوفرها Aspose.Slides.
### هل هناك أي حد لعدد العقد في SmartArt؟
يدعم SmartArt في PowerPoint عددًا كبيرًا من العقد، ولكن يوصى بإبقائه معقولًا لتحسين إمكانية القراءة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
