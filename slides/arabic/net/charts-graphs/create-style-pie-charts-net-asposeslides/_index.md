---
"date": "2025-04-15"
"description": "تعرف على كيفية أتمتة إنشاء المخطط الدائري في عروض .NET باستخدام Aspose.Slides، مما يعزز تصور البيانات بسهولة."
"title": "كيفية إنشاء مخططات دائرية وتخصيصها في عروض .NET التقديمية باستخدام Aspose.Slides"
"url": "/ar/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخططات دائرية وتخصيصها في عروض .NET التقديمية باستخدام Aspose.Slides

## مقدمة
يُعدّ إنشاء عروض تقديمية جذابة وغنية بالمعلومات أمرًا بالغ الأهمية للتواصل الفعال، سواءً كنت تعرض بيانات في العمل أو تستعرض أحدث نتائج مشروعك. ومن الطرق الفعّالة لعرض البيانات استخدام المخططات الدائرية، التي تُمثّل بإيجاز أجزاءً من الكل. مع ذلك، قد يستغرق إنشاء هذه المخططات يدويًا في برامج العروض التقديمية مثل PowerPoint وقتًا طويلاً، وقد يفتقر إلى المرونة اللازمة للتحديثات الديناميكية.

هنا يأتي دور Aspose.Slides لـ .NET. تتيح لك هذه المكتبة الشاملة إنشاء العروض التقديمية وتعديلها وتصميمها برمجيًا، مما يجعلها أداة قيّمة للمطورين الذين يرغبون في أتمتة سير عملهم وضمان الاتساق بين العروض التقديمية.

في هذا البرنامج التعليمي، سنستكشف كيفية استخدام Aspose.Slides لـ .NET لإنشاء مخططات دائرية وتخصيصها في عروضك التقديمية. ستتعلم كيفية:
- **إنشاء عرض تقديمي والوصول إلى الشرائح**
- **إضافة وتكوين المخططات الدائرية**
- **تخصيص بيانات الرسم البياني والسلسلة**
- **أنماط مخططات الفطيرة القطاعية**
- **إضافة تسميات مخصصة**
- **تكوين خصائص العرض وحفظ العرض التقديمي**

هل أنت مستعد لإنشاء مخططات دائرية رائعة بسهولة؟ هيا بنا!

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك الإعداد التالي:

### المكتبات المطلوبة
- Aspose.Slides لـ .NET (يوصى بالإصدار 21.11 أو إصدار أحدث)

### إعداد البيئة
- بيئة تطوير تعمل بنظام .NET Framework أو .NET Core/5+/6+
- محرر أكواد مثل Visual Studio

### متطلبات المعرفة
- فهم أساسي لبرمجة C#
- التعرف على المفاهيم الموجهة للكائنات

## إعداد Aspose.Slides لـ .NET
للبدء، ستحتاج إلى تثبيت مكتبة Aspose.Slides. يمكنك القيام بذلك باستخدام أيٍّ من الطرق التالية:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**وحدة تحكم مدير الحزم**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير الحزم NuGet**
- افتح مشروعك في Visual Studio.
- انتقل إلى "أدوات" > "مدير حزم NuGet" > "إدارة حزم NuGet للحل".
- ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### خطوات الحصول على الترخيص
لاستخدام Aspose.Slides، يمكنك البدء بفترة تجريبية مجانية بتنزيل ترخيص مؤقت. تفضل بزيارة [موقع Aspose](https://purchase.aspose.com/temporary-license/) للحصول عليه. للاستخدام المستمر، فكّر في شراء ترخيص كامل.

### التهيئة والإعداد الأساسي
بمجرد التثبيت، قم بتهيئة فئة العرض التقديمي، التي تمثل ملف PPTX الخاص بك:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## دليل التنفيذ
سنُقسّم عملية إنشاء المخطط الدائري إلى أقسام مُيسّرة. صُمّم كل قسم للتركيز على ميزة مُحدّدة، مما يُتيح لك بناء معرفتك تدريجيًا.

### إنشاء عرض تقديمي والوصول إلى الشرائح
**ملخص:** ابدأ بإنشاء عرض تقديمي جديد والوصول إلى الشريحة الأولى منه. هذا يُمهّد الطريق لإضافة المخططات والعناصر الأخرى.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // إنشاء فئة عرض تقديمي تمثل ملف PPTX
    Presentation presentation = new Presentation();
    
    // الوصول إلى الشريحة الأولى
    ISlide slides = presentation.Slides[0];
}
```

### إضافة وتكوين مخطط دائري
**ملخص:** تعرف على كيفية إضافة مخطط دائري إلى الشريحة الخاصة بك وتعيين عنوانه للسياق.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // إنشاء فئة عرض تقديمي تمثل ملف PPTX
    Presentation presentation = new Presentation();
    
    // الوصول إلى الشريحة الأولى
    ISlide slides = presentation.Slides[0];
    
    // إضافة مخطط بالبيانات الافتراضية إلى الشريحة
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // عنوان مخطط الإعداد
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### تخصيص بيانات الرسم البياني والسلسلة
**ملخص:** قم بتخصيص فئات البيانات والسلاسل لتناسب متطلباتك المحددة.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // إنشاء فئة عرض تقديمي تمثل ملف PPTX
    Presentation presentation = new Presentation();
    
    // الوصول إلى الشريحة الأولى
    ISlide slides = presentation.Slides[0];
    
    // إضافة مخطط بالبيانات الافتراضية إلى الشريحة
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // تعيين السلسلة الأولى لإظهار القيم
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // ضبط فهرس ورقة بيانات الرسم البياني
    int defaultWorksheetIndex = 0;
    
    // الحصول على ورقة عمل بيانات الرسم البياني
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // حذف السلسلة والفئات المولدة افتراضيًا
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // إضافة فئات جديدة
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // إضافة سلسلة جديدة
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // يتم الآن ملء بيانات السلسلة
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### تخصيص أنماط قطاعات المخطط الدائري
**ملخص:** قم بتصميم قطاعات فردية من مخططك الدائري لتعزيز الجاذبية البصرية والتأكيد على نقاط البيانات الرئيسية.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // إنشاء فئة عرض تقديمي تمثل ملف PPTX
    Presentation presentation = new Presentation();
    
    // الوصول إلى الشريحة الأولى
    ISlide slides = presentation.Slides[0];
    
    // إضافة مخطط بالبيانات الافتراضية إلى الشريحة
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // الحصول على سلسلة من الرسم البياني
    IChartSeries series = chart.ChartData.Series[0];
    
    // تخصيص أنماط القطاعات لكل نقطة بيانات في السلسلة
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // تعيين حدود القطاع
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // تعيين حدود القطاع
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // تعيين حدود القطاع
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### إضافة تسميات مخصصة إلى مخطط دائري
**ملخص:** قم بتعزيز مخططك الدائري عن طريق إضافة تسميات مخصصة لتمثيل البيانات بشكل أكثر وضوحًا.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // ضبط موضع الملصق حسب الحاجة
    }
}
```

### خاتمة
لقد تعلمتَ الآن كيفية إنشاء وتخصيص المخططات الدائرية في عروض .NET التقديمية باستخدام Aspose.Slides. تُحسّن هذه الأتمتة جهودك في تصور البيانات بشكل ملحوظ، مما يوفر الوقت ويضمن الاتساق في جميع العروض التقديمية.

لاستكشاف قدرات Aspose.Slides لـ .NET بشكل أكبر، فكر في الغوص في ميزات إضافية مثل إنشاء أنواع أخرى من المخططات أو دمج عناصر تصميم أكثر تعقيدًا في الشرائح الخاصة بك.

برمجة سعيدة!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}