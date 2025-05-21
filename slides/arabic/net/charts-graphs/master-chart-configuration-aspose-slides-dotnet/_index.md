---
"date": "2025-04-15"
"description": "تعلم كيفية تكوين عناوين المخططات والمحاور والرموز التوضيحية باستخدام Aspose.Slides لـ .NET. يغطي هذا الدليل كل شيء، من الإعداد الأساسي إلى التخصيص المتقدم."
"title": "تكوين المخطط الرئيسي في .NET باستخدام Aspose.Slides - دليل شامل"
"url": "/ar/net/charts-graphs/master-chart-configuration-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان تكوين المخططات في .NET باستخدام Aspose.Slides

## مقدمة
إنشاء مخططات بيانية جذابة بصريًا وغنية بالمعلومات أمرٌ أساسي لعرض البيانات بفعالية. سواءً كنت تُعدّ تقريرًا تجاريًا أو عرضًا تقديميًا تقنيًا، فإن تكوين عناوين المخططات ومحاورها يُحسّن بشكل كبير من سهولة القراءة والتأثير. يُرشدك هذا الدليل الشامل إلى كيفية استخدام Aspose.Slides لـ .NET لتكوين عناصر المخططات البيانية ببراعة، مثل العناوين وخصائص المحاور والرموز التوضيحية. ستتعلم كيفية الاستفادة من هذه المكتبة القوية لإنشاء عروض تقديمية احترافية بسهولة.

**ما سوف تتعلمه:**
- إنشاء عناوين المخططات وتنسيقها
- تكوين خطوط الشبكة الرئيسية والثانوية لمحاور القيمة
- تعيين خصائص النص لكل من محاور القيمة والفئة
- تخصيص تنسيق الأسطورة
- ضبط ألوان جدار الرسم البياني

هل أنت مستعد لتحويل مخططاتك البيانية إلى عروض مرئية جذابة؟ هيا بنا!

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:

- **Aspose.Slides لـ .NET**هذه المكتبة ضرورية للتعامل مع ملفات PowerPoint. تأكد من تثبيتها وتكوينها.
- **بيئة التطوير**:بيئة تطوير AC# مثل Visual Studio.
- **المعرفة الأساسية**:المعرفة ببرمجة C# وفهم مفاهيم العرض.

## إعداد Aspose.Slides لـ .NET
### تعليمات التثبيت
لاستخدام Aspose.Slides في مشروعك، اتبع خطوات التثبيت التالية:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**وحدة تحكم مدير الحزم**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير الحزم NuGet**
ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### الترخيص
- **نسخة تجريبية مجانية**:ابدأ بإصدار تجريبي مجاني لاستكشاف الميزات.
- **رخصة مؤقتة**:الحصول على ترخيص مؤقت للاختبار الموسع.
- **شراء**:للاستخدام طويل الأمد، اشترِ ترخيصًا. تفضل بزيارة [شراء Aspose](https://purchase.aspose.com/buy) لمزيد من التفاصيل.

قم بتهيئة مشروعك عن طريق إضافة التوجيهات اللازمة وإعداد مثيل عرض تقديمي أساسي:
```csharp
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Charts;

// إنشاء فئة عرض تقديمي تمثل ملف PPTX
Presentation pres = new Presentation();
```

## دليل التنفيذ
ينقسم هذا الدليل إلى أقسام، يركز كل منها على جوانب محددة من تكوين الرسم البياني باستخدام Aspose.Slides لـ .NET.

### إنشاء وتكوين عنوان الرسم البياني
**ملخص**
إضافة عنوان وصفي لرسمك البياني يُحسّن وضوحه. يشرح هذا القسم كيفية إنشاء رسم بياني وتخصيص عنوانه باستخدام خيارات تنسيق مُحددة.

#### التنفيذ خطوة بخطوة
1. **إضافة مخطط إلى الشريحة**
   انتقل إلى الشريحة الأولى في العرض التقديمي الخاص بك وأدرج مخططًا خطيًا:
   ```csharp
   ISlide slide = pres.Slides[0];
   IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
   ```
2. **تعيين عنوان الرسم البياني مع التنسيق**
   تخصيص نص العنوان وتطبيق التنسيق:
   ```csharp
   chart.HasTitle = true;
   chart.ChartTitle.AddTextFrameForOverriding("");
   IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
   chartTitle.Text = "Sample Chart";
   chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
   chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
   chartTitle.PortionFormat.FontHeight = 20;
   chartTitle.PortionFormat.FontBold = NullableBool.True;
   chartTitle.PortionFormat.FontItalic = NullableBool.True;
   ```

### تكوين خطوط شبكة محور القيمة وخصائصها
**ملخص**
خطوط الشبكة المُنسّقة بشكل صحيح على محور القيمة تُحسّن سهولة قراءة البيانات. لنُهيئ خطوط الشبكة الرئيسية والفرعية بأنماط مُحدّدة.

#### التنفيذ خطوة بخطوة
1. **الوصول إلى المحور الرأسي للرسم البياني**
   استرداد المحور الرأسي للرسم البياني الخاص بك:
   ```csharp
   IVerticalAxis verticalAxis = chart.Axes.VerticalAxis;
   ```
2. **تنسيق خطوط الشبكة الرئيسية والثانوية**
   قم بتطبيق اللون والعرض والأسلوب على خطوط الشبكة الرئيسية والثانوية:
   ```csharp
   // خطوط الشبكة الرئيسية
   verticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
   verticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
   verticalAxis.MajorGridLinesFormat.Line.Width = 5;
   verticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

   // خطوط الشبكة الثانوية
   verticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
   verticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
   verticalAxis.MinorGridLinesFormat.Line.Width = 3;
   ```
3. **تعيين تنسيق الأرقام وخصائص المحور**
   تكوين تنسيقات الأرقام وخصائص المحور لتمثيل البيانات بدقة:
   ```csharp
   verticalAxis.IsNumberFormatLinkedToSource = false;
   verticalAxis.DisplayUnit = DisplayUnitType.Thousands;
   verticalAxis.NumberFormat = "0.0%";
   verticalAxis.IsAutomaticMajorUnit = false;
   verticalAxis.IsAutomaticMaxValue = false;
   verticalAxis.IsAutomaticMinorUnit = false;
   verticalAxis.IsAutomaticMinValue = false;

   verticalAxis.MaxValue = 15f;
   verticalAxis.MinValue = -2f;
   verticalAxis.MinorUnit = 0.5f;
   verticalAxis.MajorUnit = 2.0f;
   ```

### تكوين خصائص نص محور القيمة
**ملخص**
قم بتعزيز محور القيمة باستخدام خصائص النص المخصصة لتحسين إمكانية القراءة.

#### التنفيذ خطوة بخطوة
1. **تعيين تنسيق النص للمحور الرأسي**
   تطبيق الأنماط العريضة والمائلة والألوان على النص:
   ```csharp
   IChartPortionFormat txtVal = verticalAxis.TextFormat.PortionFormat;
   txtVal.FontBold = NullableBool.True;
   txtVal.FontHeight = 16;
   txtVal.FontItalic = NullableBool.True;
   txtVal.FillFormat.FillType = FillType.Solid;
   txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
   txtVal.LatinFont = new FontData("Times New Roman");
   ```

### تكوين خطوط شبكة محور الفئة وخصائص النص
**ملخص**
إن تخصيص خطوط شبكة محور الفئة وخصائص النص يضمن أن يكون الرسم البياني الخاص بك مفيدًا وجذابًا بصريًا.

#### التنفيذ خطوة بخطوة
1. **الوصول إلى خطوط الشبكة الرئيسية/الثانوية وتنسيقها لمحور الفئة**
   استرداد وتصميم المحور الأفقي:
   ```csharp
   IHorizontalAxis horizontalAxis = chart.Axes.HorizontalAxis;

   // خطوط الشبكة الرئيسية
   horizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
   horizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
   horizontalAxis.MajorGridLinesFormat.Line.Width = 5;

   // خطوط الشبكة الثانوية
   horizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
   horizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
   horizontalAxis.MinorGridLinesFormat.Line.Width = 3;
   ```
2. **تعيين خصائص النص لمحور الفئة**
   تخصيص مظهر النص على محور الفئة:
   ```csharp
   IChartPortionFormat txtCat = horizontalAxis.TextFormat.PortionFormat;
   txtCat.FontBold = NullableBool.True;
   txtCat.FontHeight = 16;
   txtCat.FontItalic = NullableBool.True;
   txtCat.FillFormat.FillType = FillType.Solid;
   txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
   txtCat.LatinFont = new FontData("Arial");
   ```

### تكوين عنوان محور الفئة والعلامات
**ملخص**
عنوان محور الفئة الوصفي يُحسّن فهم المخطط. لنُعدّل خصائص العنوان والتسمية.

#### التنفيذ خطوة بخطوة
1. **تعيين عنوان محور الفئة مع التنسيق**
   أضف عنوانًا إلى المحور الأفقي:
   ```csharp
   horizontalAxis.HasTitle = true;
   horizontalAxis.Title.AddTextFrameForOverriding("");
   IPortion chartLabel = horizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
   chartLabel.Text = "Sample Axis";
   chartLabel.PortionFormat.FillFormat.FillType = FillType.Solid;
   chartLabel.PortionFormat.FillFormat.SolidFillColor.Color = Color.DarkBlue;
   chartLabel.PortionFormat.FontHeight = 18;
   chartLabel.PortionFormat.FontBold = NullableBool.True;
   ```

## خاتمة
بهذه الخطوات، تعلمت كيفية تهيئة المخططات البيانية بفعالية باستخدام Aspose.Slides لـ .NET. جرّب أنماطًا وتنسيقات مختلفة لجعل عروضك التقديمية مميزة.

**توصيات الكلمات الرئيسية:**
- "Aspose.Slides لـ .NET"
- "تكوين المخطط في .NET"
- تخصيص مخطط Aspose.Slides

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}