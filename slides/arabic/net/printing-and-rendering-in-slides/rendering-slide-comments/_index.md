---
"description": "استكشف كيفية عرض تعليقات الشرائح في Aspose.Slides لـ .NET من خلال دليلنا التعليمي خطوة بخطوة. خصّص مظهر التعليقات وحسّن أتمتة PowerPoint."
"linktitle": "عرض تعليقات الشرائح في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "عرض تعليقات الشرائح في Aspose.Slides"
"url": "/ar/net/printing-and-rendering-in-slides/rendering-slide-comments/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# عرض تعليقات الشرائح في Aspose.Slides

## مقدمة
أهلاً بكم في دليلنا الشامل لعرض تعليقات الشرائح باستخدام Aspose.Slides لـ .NET! Aspose.Slides مكتبة فعّالة تُمكّن المطورين من العمل بسلاسة مع عروض PowerPoint التقديمية في تطبيقات .NET الخاصة بهم. في هذا الدليل، سنركز على مهمة محددة - عرض تعليقات الشرائح - وسنشرح العملية خطوة بخطوة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- مكتبة Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET في بيئة التطوير لديك. إذا لم تكن مثبتة بعد، يمكنك تنزيلها. [هنا](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET عاملة، واحصل على فهم أساسي لـ C#.
الآن، دعونا نبدأ بالبرنامج التعليمي!
## استيراد مساحات الأسماء
في شيفرة C#، ستحتاج إلى استيراد مساحات الأسماء اللازمة لاستخدام ميزات Aspose.Slides. أضف الأسطر التالية في بداية ملفك:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;
```
## الخطوة 1: إعداد دليل المستندات الخاص بك
ابدأ بتحديد المسار إلى دليل المستندات الذي يوجد به عرض PowerPoint التقديمي:
```csharp
string dataDir = "Your Document Directory";
```
## الخطوة 2: تحديد مسار الإخراج
قم بتحديد المسار الذي تريد حفظ الصورة المقدمة فيه مع التعليقات:
```csharp
string resultPath = Path.Combine(dataDir, "OutPresBitmap_Comments.png");
```
## الخطوة 3: تحميل العرض التقديمي
قم بتحميل عرض PowerPoint باستخدام مكتبة Aspose.Slides:
```csharp
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```
## الخطوة 4: إنشاء خريطة نقطية للرسم
إنشاء كائن خريطة نقطية بالأبعاد المطلوبة:
```csharp
Bitmap bmp = new Bitmap(740, 960);
```
## الخطوة 5: تكوين خيارات العرض
تكوين خيارات العرض، بما في ذلك خيارات التخطيط للملاحظات والتعليقات:
```csharp
IRenderingOptions renderOptions = new RenderingOptions();
NotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.CommentsAreaColor = Color.Red;
notesOptions.CommentsAreaWidth = 200;
notesOptions.CommentsPosition = CommentsPositions.Right;
notesOptions.NotesPosition = NotesPositions.BottomTruncated;
renderOptions.SlidesLayoutOptions = notesOptions;
```
## الخطوة 6: تقديم الرسومات
عرض الشريحة الأولى مع التعليقات على كائن الرسوم المحدد:
```csharp
using (Graphics graphics = Graphics.FromImage(bmp))
{
    pres.Slides[0].RenderToGraphics(renderOptions, graphics);
}
```
## الخطوة 7: حفظ النتيجة
احفظ الصورة المقدمة مع التعليقات في المسار المحدد:
```csharp
bmp.Save(resultPath, ImageFormat.Png);
```
## الخطوة 8: عرض النتيجة
افتح الصورة المقدمة باستخدام عارض الصور الافتراضي:
```csharp
System.Diagnostics.Process.Start(resultPath);
```
تهانينا! لقد نجحت في عرض تعليقات الشرائح باستخدام Aspose.Slides لـ .NET.
## خاتمة
في هذا البرنامج التعليمي، استكشفنا عملية عرض تعليقات الشرائح باستخدام Aspose.Slides لـ .NET. باتباع هذا الدليل خطوة بخطوة، يمكنك تحسين إمكانيات أتمتة PowerPoint بسهولة.
## الأسئلة الشائعة
### س: هل Aspose.Slides متوافق مع أحدث إصدارات .NET Framework؟
ج: نعم، يتم تحديث Aspose.Slides بانتظام لدعم أحدث إصدارات إطار عمل .NET.
### س: هل يمكنني تخصيص مظهر التعليقات المقدمة؟
ج: بالتأكيد! يتضمن البرنامج التعليمي خيارات لتخصيص لون وعرض وموقع منطقة التعليق.
### س: أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ .NET؟
أ: استكشف الوثائق [هنا](https://reference.aspose.com/slides/net/).
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
أ: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني طلب المساعدة والدعم لـ Aspose.Slides؟
أ: قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}