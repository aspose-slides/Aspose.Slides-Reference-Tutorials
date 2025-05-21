---
"description": "تعلّم كيفية تغيير حالات SmartArt في عروض PowerPoint التقديمية باستخدام Java وAspose.Slides. طوّر مهاراتك في أتمتة العروض التقديمية."
"linktitle": "تغيير حالة SmartArt في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تغيير حالة SmartArt في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تغيير حالة SmartArt في PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية التعامل مع كائنات SmartArt في عروض PowerPoint التقديمية باستخدام Java مع مكتبة Aspose.Slides. SmartArt ميزة فعّالة في PowerPoint تتيح لك إنشاء مخططات ورسومات جذابة بصريًا.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت جافا على نظامك. يمكنك تنزيلها من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java: قم بتنزيل وتثبيت مكتبة Aspose.Slides for Java من [موقع إلكتروني](https://releases.aspose.com/slides/java/).

## استيراد الحزم
لبدء العمل مع Aspose.Slides في مشروع Java الخاص بك، قم باستيراد الحزم الضرورية:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
الآن دعنا نقسم الكود المثال المقدم إلى خطوات متعددة:
## الخطوة 1: تهيئة كائن العرض التقديمي
```java
Presentation presentation = new Presentation();
```
هنا نقوم بإنشاء جديد `Presentation` الكائن الذي يمثل عرض تقديمي في PowerPoint.
## الخطوة 2: إضافة كائن SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
تضيف هذه الخطوة كائن SmartArt إلى الشريحة الأولى من العرض التقديمي. نحدد موضع وأبعاد كائن SmartArt، بالإضافة إلى نوع التخطيط (في هذه الحالة، `BasicProcess`).
## الخطوة 3: تعيين حالة SmartArt
```java
smart.setReversed(true);
```
هنا، نحدد حالة كائن SmartArt. في هذا المثال، نعكس اتجاه SmartArt.
## الخطوة 4: التحقق من حالة SmartArt
```java
boolean flag = smart.isReversed();
```
يمكننا أيضًا التحقق من الحالة الحالية لكائن SmartArt. يسترجع هذا السطر ما إذا كان SmartArt معكوسًا أم لا، ويخزنه في `flag` عامل.
## الخطوة 5: حفظ العرض التقديمي
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
وأخيرا، نقوم بحفظ العرض التقديمي المعدل في مكان محدد على القرص.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تغيير حالة كائنات SmartArt في عروض PowerPoint التقديمية باستخدام Java ومكتبة Aspose.Slides. بفضل هذه المعرفة، يمكنك إنشاء عروض تقديمية ديناميكية وجذابة برمجيًا.
## الأسئلة الشائعة
### هل يمكنني تعديل خصائص أخرى لـ SmartArt باستخدام Aspose.Slides لـ Java؟
نعم، يمكنك تعديل جوانب مختلفة من كائنات SmartArt، مثل الألوان والأنماط والتخطيطات، باستخدام Aspose.Slides.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
نعم، يدعم Aspose.Slides عروض PowerPoint عبر إصدارات مختلفة، مما يضمن التوافق والتكامل السلس.
### هل يمكنني إنشاء تخطيطات SmartArt مخصصة باستخدام Aspose.Slides؟
بالتأكيد! يوفر Aspose.Slides واجهات برمجة تطبيقات لإنشاء تخطيطات SmartArt مخصصة مصممة خصيصًا لتلبية احتياجاتك.
### هل يوفر Aspose.Slides الدعم لتنسيقات ملفات أخرى بالإضافة إلى PowerPoint؟
نعم، يدعم Aspose.Slides مجموعة واسعة من تنسيقات الملفات، بما في ذلك PPTX، وPPT، وPDF، والمزيد.
### هل يوجد منتدى مجتمعي حيث يمكنني الحصول على المساعدة فيما يتعلق بالأسئلة المتعلقة بـ Aspose.Slides؟
نعم، يمكنك زيارة منتدى Aspose.Slides على [هنا](https://forum.aspose.com/c/slides/11) للحصول على المساعدة والمناقشات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}