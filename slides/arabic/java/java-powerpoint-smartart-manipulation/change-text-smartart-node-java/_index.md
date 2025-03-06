---
title: تغيير النص على عقدة SmartArt باستخدام Java
linktitle: تغيير النص على عقدة SmartArt باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: اكتشف كيفية تحديث نص عقدة SmartArt في PowerPoint باستخدام Java مع Aspose.Slides، مما يعزز تخصيص العرض التقديمي.
type: docs
weight: 22
url: /ar/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---
## مقدمة
يعد SmartArt في PowerPoint ميزة قوية لإنشاء مخططات جذابة بصريًا. يوفر Aspose.Slides for Java دعمًا شاملاً لمعالجة عناصر SmartArt برمجيًا. في هذا البرنامج التعليمي، سنرشدك خلال عملية تغيير النص على عقدة SmartArt باستخدام Java.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على نظامك.
- تم تنزيل Aspose.Slides لمكتبة Java والإشارة إليها في مشروع Java الخاص بك.
- الفهم الأساسي لبرمجة جافا.

## حزم الاستيراد
أولاً، قم باستيراد الحزم اللازمة للوصول إلى وظيفة Aspose.Slides ضمن كود Java الخاص بك.
```java
import com.aspose.slides.*;
```
دعنا نقسم المثال إلى عدة خطوات:
## الخطوة 1: تهيئة كائن العرض التقديمي
```java
Presentation presentation = new Presentation();
```
 إنشاء مثيل جديد لـ`Presentation` فئة للعمل مع عرض تقديمي ل PowerPoint.
## الخطوة 2: إضافة SmartArt إلى الشريحة
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
 أضف SmartArt إلى الشريحة الأولى. في هذا المثال، نستخدم`BasicCycle` تَخطِيط.
## الخطوة 3: الوصول إلى عقدة SmartArt
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
احصل على مرجع للعقدة الجذرية الثانية لـ SmartArt.
## الخطوة 4: تعيين النص على العقدة
```java
node.getTextFrame().setText("Second root node");
```
قم بتعيين النص لعقدة SmartArt المحددة.
## الخطوة 5: حفظ العرض التقديمي
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدل في موقع محدد.

## خاتمة
لقد أوضحنا في هذا البرنامج التعليمي كيفية تغيير النص على عقدة SmartArt باستخدام Java وAspose.Slides. باستخدام هذه المعرفة، يمكنك التعامل بشكل ديناميكي مع عناصر SmartArt في عروض PowerPoint التقديمية، مما يعزز جاذبيتها البصرية ووضوحها.
## الأسئلة الشائعة
### هل يمكنني تغيير تخطيط SmartArt بعد إضافته إلى الشريحة؟
 نعم، يمكنك تغيير التخطيط عن طريق الوصول إلى`SmartArt.setAllNodes(LayoutType)` طريقة.
### هل Aspose.Slides متوافق مع Java 11؟
نعم، Aspose.Slides for Java متوافق مع Java 11 والإصدارات الأحدث.
### هل يمكنني تخصيص مظهر عقد SmartArt برمجيًا؟
بالتأكيد، يمكنك تعديل خصائص مختلفة مثل اللون والحجم والشكل باستخدام Aspose.Slides API.
### هل يدعم Aspose.Slides أنواعًا أخرى من تخطيطات SmartArt؟
نعم، يدعم Aspose.Slides مجموعة واسعة من تخطيطات SmartArt، مما يسمح لك باختيار التخطيط الذي يناسب احتياجات العرض التقديمي الخاص بك.
### أين يمكنني العثور على المزيد من الموارد والدعم لـ Aspose.Slides؟
 يمكنك زيارة[Aspose.Slides الوثائق](https://reference.aspose.com/slides/java/) للحصول على مراجع API مفصلة والبرامج التعليمية. بالإضافة إلى ذلك، يمكنك طلب المساعدة من[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) أو فكر في شراء أ[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) للحصول على الدعم المهني.