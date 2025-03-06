---
title: أضف العقد في موضع محدد في SmartArt باستخدام Java
linktitle: أضف العقد في موضع محدد في SmartArt باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: اكتشف كيفية إضافة العقد في مواضع معينة في SmartArt باستخدام Java مع Aspose.Slides. قم بإنشاء عروض تقديمية ديناميكية دون عناء.
weight: 16
url: /ar/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة العقد في مواضع محددة في SmartArt باستخدام Java مع Aspose.Slides. SmartArt هي ميزة في PowerPoint تسمح لك بإنشاء رسوم بيانية ومخططات جذابة بصريًا.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  تم تنزيل Aspose.Slides لمكتبة Java. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
3. المعرفة الأساسية بلغة البرمجة جافا.

## حزم الاستيراد
أولاً، لنستورد الحزم الضرورية في كود Java الخاص بنا:
```java
import com.aspose.slides.*;
import java.io.File;
```
## الخطوة 1: إنشاء مثيل العرض التقديمي
ابدأ بإنشاء مثيل لفئة العرض التقديمي:
```java
Presentation pres = new Presentation();
```
## الخطوة 2: الوصول إلى شريحة العرض التقديمي
قم بالوصول إلى الشريحة التي تريد إضافة SmartArt إليها:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 3: إضافة شكل SmartArt
إضافة شكل SmartArt إلى الشريحة:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## الخطوة 4: الوصول إلى عقدة SmartArt
قم بالوصول إلى عقدة SmartArt في الفهرس المطلوب:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## الخطوة 5: إضافة عقدة فرعية في موضع محدد
أضف عقدة فرعية جديدة في موضع محدد في العقدة الأصلية:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## الخطوة 6: إضافة نص إلى العقدة
قم بتعيين النص للعقدة المضافة حديثًا:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## الخطوة 7: احفظ العرض التقديمي
حفظ العرض التقديمي المعدل:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية إضافة العقد في مواضع معينة في SmartArt باستخدام Java مع Aspose.Slides. باتباع هذه الخطوات، يمكنك التعامل مع أشكال SmartArt برمجيًا لإنشاء عروض تقديمية ديناميكية.
## الأسئلة الشائعة
### هل يمكنني إضافة عقد متعددة في وقت واحد؟
نعم، يمكنك إضافة عقد متعددة برمجيًا عن طريق التكرار على المواضع المطلوبة.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides تنسيقات PowerPoint المختلفة، مما يضمن التوافق مع معظم الإصدارات.
### هل يمكنني تخصيص مظهر عقد SmartArt؟
نعم، يمكنك تخصيص مظهر العقد، بما في ذلك حجمها ولونها ونمطها.
### هل يقدم Aspose.Slides الدعم للغات البرمجة الأخرى؟
نعم، يوفر Aspose.Slides مكتبات للعديد من لغات البرمجة، بما في ذلك .NET وPython.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
