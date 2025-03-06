---
title: إضافة إطار فيديو في PowerPoint
linktitle: إضافة إطار فيديو في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية دمج محتوى الفيديو بسلاسة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. تحتوي شرائحك على عناصر الوسائط المتعددة لإشراك جمهورك.
weight: 17
url: /ar/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إطار فيديو في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة إطار فيديو إلى عرض PowerPoint التقديمي باستخدام Aspose.Slides for Java. باتباع هذه التعليمات خطوة بخطوة، ستتمكن من دمج محتوى الفيديو بسهولة في عروضك التقديمية.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك
- تم تنزيل Aspose.Slides لمكتبة Java وإعدادها في مشروع Java الخاص بك
## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة للاستفادة من وظائف Aspose.Slides في كود Java الخاص بك. 
```java
import com.aspose.slides.*;

import java.io.File;
```
## الخطوة 1: إعداد دليل المستندات
تأكد من إعداد دليل لتخزين ملفات PowerPoint الخاصة بك.
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: إنشاء كائن العرض التقديمي
 إنشاء مثيل`Presentation` فئة لتمثيل ملف PowerPoint.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة إطار فيديو إلى الشريحة
احصل على الشريحة الأولى وأضف إطار فيديو إليها.
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## الخطوة 4: ضبط وضع التشغيل ومستوى الصوت
اضبط وضع التشغيل وحجم إطار الفيديو.
```java
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## الخطوة 5: حفظ العرض التقديمي
احفظ ملف PowerPoint المعدل على القرص.
```java
pres.save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة إطار فيديو إلى عرض PowerPoint التقديمي باستخدام Aspose.Slides لـ Java. قم بتحسين عروضك التقديمية من خلال دمج عناصر الوسائط المتعددة لإشراك جمهورك بشكل فعال.
## الأسئلة الشائعة
### هل يمكنني إضافة مقاطع فيديو بأي تنسيق إلى عرض PowerPoint التقديمي؟
يدعم Aspose.Slides تنسيقات الفيديو المختلفة مثل AVI وWMV وMP4 والمزيد. تأكد من أن التنسيق متوافق مع برنامج PowerPoint.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من Java؟
نعم، Aspose.Slides for Java متوافق مع الإصدار 6 من JDK والإصدارات الأحدث.
### كيف يمكنني ضبط حجم وموضع إطار الفيديو؟
 يمكنك تخصيص أبعاد وإحداثيات إطار الفيديو عن طريق تعديل المعلمات في ملف`addVideoFrame` طريقة.
### هل يمكنني التحكم في إعدادات تشغيل الفيديو؟
نعم، يمكنك ضبط وضع التشغيل وحجم إطار الفيديو وفقًا لتفضيلاتك.
### أين يمكنني العثور على مزيد من الدعم والموارد لـ Aspose.Slides؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة والتوثيق ودعم المجتمع.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
