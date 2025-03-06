---
title: تغيير حالة SmartArt في PowerPoint باستخدام Java
linktitle: تغيير حالة SmartArt في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تغيير حالات SmartArt في عروض PowerPoint التقديمية باستخدام Java وAspose.Slides. تعزيز مهارات أتمتة العرض التقديمي الخاص بك.
weight: 21
url: /ar/java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
ستتعلم في هذا البرنامج التعليمي كيفية التعامل مع كائنات SmartArt في عروض PowerPoint التقديمية باستخدام Java مع مكتبة Aspose.Slides. SmartArt هي ميزة قوية في PowerPoint تسمح لك بإنشاء مخططات ورسومات جذابة بصريًا.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1.  Java Development Kit (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: قم بتنزيل وتثبيت مكتبة Aspose.Slides for Java من[موقع إلكتروني](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
لبدء العمل مع Aspose.Slides في مشروع Java الخاص بك، قم باستيراد الحزم الضرورية:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
لنقم الآن بتقسيم رمز المثال المقدم إلى خطوات متعددة:
## الخطوة 1: تهيئة كائن العرض التقديمي
```java
Presentation presentation = new Presentation();
```
 هنا نقوم بإنشاء جديد`Presentation` كائن يمثل عرض تقديمي لـ PowerPoint.
## الخطوة 2: إضافة كائن SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
 تضيف هذه الخطوة كائن SmartArt إلى الشريحة الأولى من العرض التقديمي. نقوم بتحديد موضع وأبعاد كائن SmartArt، بالإضافة إلى نوع التخطيط (في هذه الحالة،`BasicProcess`).
## الخطوة 3: تعيين حالة SmartArt
```java
smart.setReversed(true);
```
هنا، قمنا بتعيين حالة كائن SmartArt. في هذا المثال، نقوم بعكس اتجاه SmartArt.
## الخطوة 4: التحقق من حالة SmartArt
```java
boolean flag = smart.isReversed();
```
 يمكننا أيضًا التحقق من الحالة الحالية لكائن SmartArt. يسترد هذا السطر ما إذا كان SmartArt معكوسًا أم لا ويخزنه في الملف`flag` عامل.
## الخطوة 5: حفظ العرض التقديمي
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
وأخيرًا، نقوم بحفظ العرض التقديمي المعدل في موقع محدد على القرص.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تغيير حالة كائنات SmartArt في عروض PowerPoint التقديمية باستخدام Java ومكتبة Aspose.Slides. باستخدام هذه المعرفة، يمكنك إنشاء عروض تقديمية ديناميكية وجذابة برمجيًا.
## الأسئلة الشائعة
### هل يمكنني تعديل خصائص SmartArt الأخرى باستخدام Aspose.Slides لـ Java؟
نعم، يمكنك تعديل جوانب مختلفة من كائنات SmartArt، مثل الألوان والأنماط والتخطيطات، باستخدام Aspose.Slides.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
نعم، يدعم Aspose.Slides عروض PowerPoint التقديمية عبر إصدارات مختلفة، مما يضمن التوافق والتكامل السلس.
### هل يمكنني إنشاء تخطيطات SmartArt مخصصة باستخدام Aspose.Slides؟
قطعاً! يوفر Aspose.Slides واجهات برمجة التطبيقات لإنشاء تخطيطات SmartArt مخصصة مصممة خصيصًا لتلبية احتياجاتك الخاصة.
### هل يقدم Aspose.Slides الدعم لتنسيقات الملفات الأخرى إلى جانب PowerPoint؟
نعم، يدعم Aspose.Slides مجموعة واسعة من تنسيقات الملفات، بما في ذلك PPTX وPPT وPDF والمزيد.
### هل يوجد منتدى مجتمعي حيث يمكنني الحصول على المساعدة بشأن الأسئلة المتعلقة بـ Aspose.Slides؟
 نعم، يمكنك زيارة منتدى Aspose.Slides على[هنا](https://forum.aspose.com/c/slides/11) للمساعدة والمناقشات.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
