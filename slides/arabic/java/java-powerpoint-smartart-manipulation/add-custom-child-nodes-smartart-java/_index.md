---
title: أضف العقد التابعة المخصصة في SmartArt باستخدام Java
linktitle: أضف العقد التابعة المخصصة في SmartArt باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة عقد فرعية مخصصة إلى SmartArt في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides. قم بتحسين الشرائح الخاصة بك باستخدام الرسومات الاحترافية دون عناء.
weight: 11
url: /ar/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
SmartArt هي ميزة قوية في PowerPoint تتيح للمستخدمين إنشاء رسومات ذات مظهر احترافي بسرعة وسهولة. في هذا البرنامج التعليمي، سوف نتعلم كيفية إضافة العقد الفرعية المخصصة إلى SmartArt باستخدام Java مع Aspose.Slides.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. Java Development Kit (JDK): تأكد من تثبيت Java على نظامك.
2.  Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من[هنا](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
```
## الخطوة 1: قم بتحميل العرض التقديمي
قم بتحميل عرض PowerPoint التقديمي حيث تريد إضافة العقد الفرعية المخصصة إلى SmartArt:
```java
String dataDir = "Your Document Directory";
// قم بتحميل العرض التقديمي المطلوب
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## الخطوة 2: إضافة SmartArt إلى الشريحة
الآن، دعونا نضيف SmartArt إلى الشريحة:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## الخطوة 3: نقل شكل SmartArt
نقل شكل SmartArt إلى موضع جديد:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## الخطوة 4: تغيير عرض الشكل
تغيير عرض شكل SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## الخطوة 5: تغيير ارتفاع الشكل
تغيير ارتفاع شكل SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## الخطوة 6: تدوير الشكل
تدوير شكل SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## الخطوة 7: احفظ العرض التقديمي
وأخيرا، احفظ العرض التقديمي المعدل:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إضافة العقد الفرعية المخصصة إلى SmartArt باستخدام Java مع Aspose.Slides. باتباع هذه الخطوات، يمكنك تحسين عروضك التقديمية برسومات مخصصة، مما يجعلها أكثر جاذبية واحترافية.
## الأسئلة الشائعة
### هل يمكنني إضافة أنواع مختلفة من تخطيطات SmartArt باستخدام Aspose.Slides لـ Java؟
نعم، يدعم Aspose.Slides for Java العديد من تخطيطات SmartArt، مما يسمح لك باختيار التخطيط الذي يناسب احتياجات العرض التقديمي الخاص بك.
### هل Aspose.Slides for Java متوافق مع الإصدارات المختلفة من PowerPoint؟
تم تصميم Aspose.Slides for Java للعمل بسلاسة مع إصدارات مختلفة من PowerPoint، مما يضمن التوافق والاتساق عبر الأنظمة الأساسية.
### هل يمكنني تخصيص مظهر أشكال SmartArt برمجياً؟
قطعاً! باستخدام Aspose.Slides for Java، يمكنك تخصيص مظهر أشكال SmartArt وحجمها ولونها وتخطيطها برمجيًا لتناسب تفضيلات التصميم الخاصة بك.
### هل يوفر Aspose.Slides for Java الوثائق والدعم؟
نعم، يمكنك العثور على وثائق شاملة والوصول إلى منتديات دعم المجتمع على موقع Aspose.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides for Java من موقع الويب لاستكشاف ميزاته وإمكانياته قبل إجراء عملية الشراء[هنا](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
