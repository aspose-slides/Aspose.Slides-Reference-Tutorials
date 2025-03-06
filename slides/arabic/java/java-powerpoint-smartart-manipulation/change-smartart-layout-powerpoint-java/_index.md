---
title: تغيير تخطيط SmartArt في PowerPoint باستخدام Java
linktitle: تغيير تخطيط SmartArt في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية التعامل مع تخطيطات SmartArt في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides for Java.
weight: 19
url: /ar/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تغيير تخطيط SmartArt في PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية التعامل مع تخطيطات SmartArt في عروض PowerPoint التقديمية باستخدام Java. SmartArt هي ميزة قوية في PowerPoint تسمح للمستخدمين بإنشاء رسومات جذابة بصريًا لأغراض متعددة، مثل توضيح العمليات والتسلسلات الهرمية والعلاقات والمزيد.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. بيئة تطوير Java: تأكد من تثبيت Java Development Kit (JDK) على نظامك.
2.  مكتبة Aspose.Slides: قم بتنزيل وتثبيت مكتبة Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/slides/java/).
3. الفهم الأساسي لجافا: الإلمام بأساسيات لغة برمجة جافا سيكون مفيدًا.
4. بيئة التطوير المتكاملة (IDE): اختر بيئة تطوير متكاملة (IDE) تفضلها، مثل Eclipse أو IntelliJ IDEA.

## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## الخطوة 1: إعداد بيئة مشروع Java الخاصة بك
تأكد من إعداد مشروع Java الخاص بك بشكل صحيح في IDE الذي اخترته. قم بإنشاء مشروع Java جديد وقم بتضمين مكتبة Aspose.Slides في تبعيات مشروعك.
## الخطوة 2: إنشاء عرض تقديمي جديد
قم بإنشاء مثيل لكائن عرض تقديمي جديد لإنشاء عرض تقديمي جديد لـ PowerPoint.
```java
Presentation presentation = new Presentation();
```
## الخطوة 3: إضافة رسم SmartArt
أضف رسم SmartArt إلى العرض التقديمي الخاص بك. حدد موضع وأبعاد رسم SmartArt على الشريحة.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## الخطوة 4: تغيير تخطيط SmartArt
قم بتغيير تخطيط رسم SmartArt إلى نوع التخطيط المطلوب.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي المعدل في دليل محدد على نظامك.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## خاتمة
تعد معالجة تخطيطات SmartArt في عروض PowerPoint التقديمية باستخدام Java عملية مباشرة مع Aspose.Slides for Java. باتباع هذا البرنامج التعليمي، يمكنك بسهولة تعديل رسومات SmartArt لتناسب احتياجات العرض التقديمي الخاص بك.
## الأسئلة الشائعة
### هل يمكنني تخصيص مظهر رسومات SmartArt باستخدام Aspose.Slides لـ Java؟
نعم، يمكنك تخصيص جوانب مختلفة من رسومات SmartArt، مثل الألوان والأنماط والتأثيرات.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
يدعم Aspose.Slides عروض PowerPoint التقديمية التي تم إنشاؤها في إصدارات مختلفة من PowerPoint، مما يضمن التوافق عبر الأنظمة الأساسية المختلفة.
### هل يقدم Aspose.Slides الدعم للغات البرمجة الأخرى؟
نعم، يتوفر Aspose.Slides للعديد من لغات البرمجة، بما في ذلك .NET وPython وJavaScript.
### هل يمكنني إنشاء رسومات SmartArt من البداية باستخدام Aspose.Slides؟
بالتأكيد، يمكنك إنشاء رسومات SmartArt برمجيًا أو تعديل الرسومات الموجودة لتلبية متطلباتك.
### هل يوجد منتدى مجتمعي حيث يمكنني طلب المساعدة فيما يتعلق بـ Aspose.Slides؟
 نعم، يمكنك زيارة منتدى Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11) لطرح الأسئلة والتفاعل مع المجتمع.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
