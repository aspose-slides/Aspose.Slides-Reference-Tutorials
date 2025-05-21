---
"description": "تعرف على كيفية تحسين عروض PowerPoint الخاصة بك عن طريق إضافة إطارات فيديو من مصادر الويب باستخدام Aspose.Slides لـ Java."
"linktitle": "إضافة إطار فيديو من مصدر الويب في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة إطار فيديو من مصدر الويب في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إطار فيديو من مصدر الويب في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنتعلم كيفية إضافة إطار فيديو من مصدر ويب، مثل يوتيوب، إلى عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. باتباع هذه التعليمات خطوة بخطوة، ستتمكن من تحسين عروضك التقديمية من خلال دمج عناصر وسائط متعددة جذابة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على نظامك.
- تم تنزيل مكتبة Aspose.Slides لجافا وإضافتها إلى مشروع جافا الخاص بك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- اتصال إنترنت نشط للوصول إلى مصدر الويب (على سبيل المثال، YouTube).

## استيراد الحزم
أولاً، قم باستيراد الحزم اللازمة إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## الخطوة 1: إنشاء كائن عرض تقديمي في PowerPoint
قم بتهيئة كائن العرض التقديمي، الذي يمثل عرض تقديمي في PowerPoint:
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة إطار فيديو
الآن، لنُضِف إطار فيديو إلى العرض التقديمي. سيحتوي هذا الإطار على الفيديو من مصدر الويب. سنستخدم دالة addVideoFrame:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
استبدل "VIDEO_ID" بمعرف فيديو YouTube الذي تريد تضمينه.
## الخطوة 3: ضبط وضع تشغيل الفيديو
اضبط وضع تشغيل إطار الفيديو. في هذا المثال، سنضبطه على "تلقائي":
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## الخطوة 4: تحميل الصورة المصغرة
لتحسين المظهر البصري، سنحمّل الصورة المصغّرة للفيديو. تتضمن هذه الخطوة جلب الصورة المصغّرة من مصدر الويب:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## الخطوة 5: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
استبدل "YOUR_DIRECTORY" بالدليل الذي تريد حفظ العرض التقديمي فيه.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة إطار فيديو من مصدر ويب في PowerPoint باستخدام Aspose.Slides لجافا. إن دمج عناصر الوسائط المتعددة، مثل مقاطع الفيديو، يُحسّن بشكل كبير من تأثير عروضك التقديمية وتفاعل الجمهور معها.
## الأسئلة الشائعة
### هل يمكنني إضافة مقاطع فيديو من مصادر أخرى غير اليوتيوب؟
نعم، يمكنك إضافة مقاطع فيديو من مصادر ويب مختلفة طالما أنها توفر رابطًا قابلًا للتضمين.
### هل أحتاج إلى اتصال بالإنترنت لتشغيل الفيديو المضمن؟
نعم، يلزم وجود اتصال نشط بالإنترنت لبث الفيديو من مصدر الويب.
### هل يمكنني تخصيص مظهر إطار الفيديو؟
بالتأكيد! يوفر Aspose.Slides خيارات شاملة لتخصيص مظهر وسلوك إطارات الفيديو.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides مجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق عبر منصات مختلفة.
### أين يمكنني العثور على المزيد من الموارد والدعم لـ Aspose.Slides؟
يمكنك زيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة والتوثيق ودعم المجتمع.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}