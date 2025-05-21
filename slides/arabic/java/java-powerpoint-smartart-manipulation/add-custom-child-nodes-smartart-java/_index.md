---
"description": "تعرّف على كيفية إضافة عُقد فرعية مخصصة إلى SmartArt في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides. حسّن عروضك التقديمية برسومات احترافية بكل سهولة."
"linktitle": "إضافة عقد فرعية مخصصة في SmartArt باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة عقد فرعية مخصصة في SmartArt باستخدام Java"
"url": "/ar/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة عقد فرعية مخصصة في SmartArt باستخدام Java

## مقدمة
SmartArt ميزة فعّالة في PowerPoint تُمكّن المستخدمين من إنشاء رسومات احترافية بسرعة وسهولة. في هذا البرنامج التعليمي، سنتعلم كيفية إضافة عُقد فرعية مخصصة إلى SmartArt باستخدام Java مع Aspose.Slides.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت Java على نظامك.
2. Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من [هنا](https://releases.aspose.com/slides/java/).

## استيراد الحزم
للبدء، قم باستيراد الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
```
## الخطوة 1: تحميل العرض التقديمي
قم بتحميل عرض PowerPoint حيث تريد إضافة عقد فرعية مخصصة إلى SmartArt:
```java
String dataDir = "Your Document Directory";
// قم بتحميل العرض التقديمي المطلوب
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## الخطوة 2: إضافة SmartArt إلى الشريحة
الآن، دعنا نضيف SmartArt إلى الشريحة:
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
## الخطوة 7: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إضافة عُقد فرعية مخصصة إلى SmartArt باستخدام جافا مع Aspose.Slides. باتباع هذه الخطوات، يمكنك تحسين عروضك التقديمية برسومات مخصصة، مما يجعلها أكثر جاذبية واحترافية.
## الأسئلة الشائعة
### هل يمكنني إضافة أنواع مختلفة من تخطيطات SmartArt باستخدام Aspose.Slides لـ Java؟
نعم، يدعم Aspose.Slides for Java تخطيطات SmartArt المختلفة، مما يسمح لك باختيار التخطيط الذي يناسب احتياجات العرض التقديمي لديك بشكل أفضل.
### هل Aspose.Slides for Java متوافق مع الإصدارات المختلفة من PowerPoint؟
تم تصميم Aspose.Slides for Java للعمل بسلاسة مع إصدارات مختلفة من PowerPoint، مما يضمن التوافق والتناسق عبر الأنظمة الأساسية.
### هل يمكنني تخصيص مظهر أشكال SmartArt برمجيًا؟
بالتأكيد! مع Aspose.Slides لجافا، يمكنك تخصيص مظهر وحجم ولون وتخطيط أشكال SmartArt برمجيًا لتناسب تفضيلاتك التصميمية.
### هل يوفر Aspose.Slides for Java الوثائق والدعم؟
نعم، يمكنك العثور على وثائق شاملة والوصول إلى منتديات دعم المجتمع على موقع Aspose.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides for Java من الموقع الإلكتروني لاستكشاف ميزاته وقدراته قبل إجراء عملية شراء [هنا](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}