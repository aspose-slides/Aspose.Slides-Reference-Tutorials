---
title: عرض تعليقات الشرائح في Aspose.Slides
linktitle: عرض تعليقات الشرائح في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: اكتشف كيفية عرض تعليقات الشرائح في Aspose.Slides لـ .NET من خلال برنامجنا التعليمي خطوة بخطوة. قم بتخصيص مظهر التعليق ورفع مستوى أتمتة PowerPoint.
type: docs
weight: 12
url: /ar/net/printing-and-rendering-in-slides/rendering-slide-comments/
---
## مقدمة
مرحبًا بك في برنامجنا التعليمي الشامل حول عرض تعليقات الشرائح باستخدام Aspose.Slides لـ .NET! Aspose.Slides هي مكتبة قوية تمكن المطورين من العمل بسلاسة مع عروض PowerPoint التقديمية في تطبيقات .NET الخاصة بهم. في هذا الدليل، سنركز على مهمة محددة - عرض تعليقات الشرائح - ونرشدك خلال العملية خطوة بخطوة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
-  Aspose.Slides for .NET Library: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل، يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET عاملة، واحصل على فهم أساسي لـ C#.
الآن، دعونا نبدأ مع البرنامج التعليمي!
## استيراد مساحات الأسماء
في كود C# الخاص بك، تحتاج إلى استيراد مساحات الأسماء الضرورية لاستخدام ميزات Aspose.Slides. أضف الأسطر التالية في بداية ملفك:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;
```
## الخطوة 1: قم بإعداد دليل المستندات الخاص بك
ابدأ بتحديد المسار إلى دليل المستند الخاص بك حيث يوجد عرض PowerPoint التقديمي:
```csharp
string dataDir = "Your Document Directory";
```
## الخطوة 2: تحديد مسار الإخراج
حدد المسار الذي تريد حفظ الصورة المعروضة به مع التعليقات:
```csharp
string resultPath = Path.Combine(dataDir, "OutPresBitmap_Comments.png");
```
## الخطوة 3: قم بتحميل العرض التقديمي
قم بتحميل عرض PowerPoint التقديمي باستخدام مكتبة Aspose.Slides:
```csharp
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```
## الخطوة 4: إنشاء صورة نقطية للعرض
قم بإنشاء كائن نقطي بالأبعاد المطلوبة:
```csharp
Bitmap bmp = new Bitmap(740, 960);
```
## الخطوة 5: تكوين خيارات العرض
قم بتكوين خيارات العرض، بما في ذلك خيارات التخطيط للملاحظات والتعليقات:
```csharp
IRenderingOptions renderOptions = new RenderingOptions();
NotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.CommentsAreaColor = Color.Red;
notesOptions.CommentsAreaWidth = 200;
notesOptions.CommentsPosition = CommentsPositions.Right;
notesOptions.NotesPosition = NotesPositions.BottomTruncated;
renderOptions.SlidesLayoutOptions = notesOptions;
```
## الخطوة 6: تقديم إلى الرسومات
قم بعرض الشريحة الأولى مع التعليقات على كائن الرسومات المحدد:
```csharp
using (Graphics graphics = Graphics.FromImage(bmp))
{
    pres.Slides[0].RenderToGraphics(renderOptions, graphics);
}
```
## الخطوة 7: حفظ النتيجة
احفظ الصورة المقدمة مع التعليقات على المسار المحدد:
```csharp
bmp.Save(resultPath, ImageFormat.Png);
```
## الخطوة 8: عرض النتيجة
افتح الصورة المعروضة باستخدام عارض الصور الافتراضي:
```csharp
System.Diagnostics.Process.Start(resultPath);
```
تهانينا! لقد نجحت في تقديم تعليقات الشرائح باستخدام Aspose.Slides لـ .NET.
## خاتمة
في هذا البرنامج التعليمي، استكشفنا عملية عرض تعليقات الشرائح باستخدام Aspose.Slides لـ .NET. باتباع الدليل الموضح خطوة بخطوة، يمكنك تحسين قدرات التشغيل الآلي لبرنامج PowerPoint بسهولة.
## أسئلة مكررة
### س: هل Aspose.Slides متوافق مع أحدث إصدارات .NET Framework؟
ج: نعم، يتم تحديث Aspose.Slides بانتظام لدعم أحدث إصدارات إطار عمل .NET.
### س: هل يمكنني تخصيص مظهر التعليقات المقدمة؟
ج: بالتأكيد! يتضمن البرنامج التعليمي خيارات لتخصيص لون منطقة التعليق وعرضها وموضعها.
### س: أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ .NET؟
 ج: اكتشف الوثائق[هنا](https://reference.aspose.com/slides/net/).
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 ج: يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني طلب المساعدة والدعم بشأن Aspose.Slides؟
ج: قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع.