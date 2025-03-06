---
title: إضافة إطار الصوت في PowerPoint
linktitle: إضافة إطار الصوت في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة إطارات صوتية إلى عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. ارفع مستوى عروضك التقديمية باستخدام عناصر صوتية جذابة دون عناء.
weight: 12
url: /ar/java/java-powerpoint-shape-media-insertion/add-audio-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
يمكن أن يؤدي تعزيز العروض التقديمية باستخدام العناصر الصوتية إلى زيادة تأثيرها ومشاركتها بشكل كبير. باستخدام Aspose.Slides for Java، يصبح دمج الإطارات الصوتية في عروض PowerPoint التقديمية عملية سلسة. سيرشدك هذا البرنامج التعليمي خلال عملية إضافة إطارات صوتية إلى عروضك التقديمية خطوة بخطوة باستخدام Aspose.Slides for Java.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت Java على نظامك.
2.  Aspose.Slides لمكتبة Java: قم بتنزيل وتثبيت Aspose.Slides لمكتبة Java. يمكنك تنزيله من[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).
3. ملف صوتي: قم بإعداد الملف الصوتي (على سبيل المثال، تنسيق WAV) الذي تريد إضافته إلى العرض التقديمي الخاص بك.
## حزم الاستيراد
قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## الخطوة 1: قم بإعداد دليل المشروع الخاص بك
تأكد من إعداد بنية الدليل لمشروعك. إذا لم يكن الأمر كذلك، قم بإنشاء واحد لتنظيم ملفاتك بشكل فعال.
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## الخطوة 2: إنشاء مثيل لفئة العرض التقديمي
 إنشاء مثيل`Presentation` فئة لتمثيل عرض PowerPoint التقديمي.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: احصل على الشريحة وتحميل الملف الصوتي
استرجع الشريحة الأولى وقم بتحميل الملف الصوتي من الدليل الخاص بك.
```java
ISlide sld = pres.getSlides().get_Item(0);
FileInputStream fstr = new FileInputStream(dataDir + "sampleaudio.wav");
```
## الخطوة 4: إضافة إطار الصوت
أضف إطار الصوت إلى الشريحة.
```java
IAudioFrame audioFrame = sld.getShapes().addAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## الخطوة 5: تعيين خصائص الصوت
قم بتعيين خصائص مثل التشغيل عبر الشرائح وإرجاع الصوت ووضع التشغيل ومستوى الصوت.
```java
audioFrame.setPlayAcrossSlides(true);
audioFrame.setRewindAudio(true);
audioFrame.setPlayMode(AudioPlayModePreset.Auto);
audioFrame.setVolume(AudioVolumeMode.Loud);
```
## الخطوة 6: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل بإطار الصوت المضاف.
```java
pres.save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```

## خاتمة
يمكن أن يؤدي دمج العناصر الصوتية في عروض PowerPoint التقديمية إلى تعزيز فعاليتها وجذب جمهورك. مع Aspose.Slides for Java، تصبح عملية إضافة الإطارات الصوتية سهلة، مما يسمح لك بإنشاء عروض تقديمية ديناميكية وجذابة دون عناء.

## الأسئلة الشائعة
### هل يمكنني إضافة ملفات صوتية بتنسيقات مختلفة إلى العرض التقديمي الخاص بي؟
نعم، يدعم Aspose.Slides for Java تنسيقات صوتية متنوعة، بما في ذلك WAV وMP3 والمزيد.
### هل من الممكن ضبط توقيت تشغيل الصوت في الشرائح؟
قطعاً. يمكنك مزامنة تشغيل الصوت مع انتقالات شرائح معينة باستخدام Aspose.Slides لـ Java.
### هل يوفر Aspose.Slides for Java الدعم للتوافق عبر الأنظمة الأساسية؟
نعم، يمكنك إنشاء عروض PowerPoint التقديمية باستخدام إطارات صوتية مضمنة متوافقة عبر منصات مختلفة.
### هل يمكنني تخصيص مظهر مشغل الصوت في العرض التقديمي؟
يوفر Aspose.Slides for Java خيارات تخصيص واسعة النطاق، مما يسمح لك بتخصيص مظهر مشغل الصوت ليناسب تفضيلاتك.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ Java؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Slides for Java من موقعهم[موقع إلكتروني](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
