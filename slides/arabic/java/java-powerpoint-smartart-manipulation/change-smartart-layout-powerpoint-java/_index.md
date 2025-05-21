---
"description": "تعرف على كيفية التعامل مع تخطيطات SmartArt في عروض PowerPoint باستخدام Java مع Aspose.Slides for Java."
"linktitle": "تغيير تخطيط SmartArt في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تغيير تخطيط SmartArt في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تغيير تخطيط SmartArt في PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية التعامل مع تخطيطات SmartArt في عروض PowerPoint التقديمية باستخدام Java. SmartArt ميزة فعّالة في PowerPoint، تتيح للمستخدمين إنشاء رسومات جذابة بصريًا لأغراض متنوعة، مثل توضيح العمليات والتسلسلات الهرمية والعلاقات وغيرها.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. بيئة تطوير Java: تأكد من تثبيت Java Development Kit (JDK) على نظامك.
2. مكتبة Aspose.Slides: قم بتنزيل وتثبيت مكتبة Aspose.Slides for Java من [هنا](https://releases.aspose.com/slides/java/).
3. الفهم الأساسي للغة جافا: إن الإلمام بأساسيات لغة برمجة جافا سيكون مفيدًا.
4. بيئة التطوير المتكاملة (IDE): اختر بيئة التطوير المتكاملة المفضلة لديك، مثل Eclipse أو IntelliJ IDEA.

## استيراد الحزم
للبدء، قم باستيراد الحزم اللازمة إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## الخطوة 1: إعداد بيئة مشروع Java الخاص بك
تأكد من إعداد مشروع جافا الخاص بك بشكل صحيح في بيئة التطوير المتكاملة التي اخترتها. أنشئ مشروع جافا جديدًا وأدرج مكتبة Aspose.Slides في تبعيات مشروعك.
## الخطوة 2: إنشاء عرض تقديمي جديد
قم بإنشاء كائن عرض تقديمي جديد لإنشاء عرض تقديمي جديد في PowerPoint.
```java
Presentation presentation = new Presentation();
```
## الخطوة 3: إضافة رسم SmartArt
أضف رسم SmartArt إلى عرضك التقديمي. حدد موضع وأبعاد رسم SmartArt على الشريحة.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## الخطوة 4: تغيير تخطيط SmartArt
قم بتغيير تخطيط رسم SmartArt إلى نوع التخطيط الذي تريده.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل في الدليل المحدد على نظامك.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## خاتمة
يُعدّ التعامل مع تخطيطات SmartArt في عروض PowerPoint التقديمية باستخدام Java عملية سهلة مع Aspose.Slides for Java. باتباع هذا البرنامج التعليمي، يمكنك بسهولة تعديل رسومات SmartArt لتناسب احتياجات عرضك التقديمي.
## الأسئلة الشائعة
### هل يمكنني تخصيص مظهر رسومات SmartArt باستخدام Aspose.Slides لـ Java؟
نعم، يمكنك تخصيص جوانب مختلفة من رسومات SmartArt، مثل الألوان والأنماط والتأثيرات.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
يدعم Aspose.Slides عروض PowerPoint التي تم إنشاؤها في إصدارات مختلفة من PowerPoint، مما يضمن التوافق عبر منصات مختلفة.
### هل يوفر Aspose.Slides الدعم للغات البرمجة الأخرى؟
نعم، Aspose.Slides متاح للعديد من لغات البرمجة، بما في ذلك .NET، وPython، وJavaScript.
### هل يمكنني إنشاء رسومات SmartArt من الصفر باستخدام Aspose.Slides؟
بالتأكيد، يمكنك إنشاء رسومات SmartArt برمجيًا أو تعديل الرسومات الموجودة لتلبية متطلباتك.
### هل يوجد منتدى مجتمعي حيث يمكنني طلب المساعدة فيما يتعلق بـ Aspose.Slides؟
نعم، يمكنك زيارة منتدى Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11) لطرح الأسئلة والتفاعل مع المجتمع.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}