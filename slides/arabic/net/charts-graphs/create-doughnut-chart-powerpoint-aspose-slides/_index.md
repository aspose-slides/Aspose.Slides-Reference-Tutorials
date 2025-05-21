---
"date": "2025-04-15"
"description": "تعرف على كيفية إنشاء مخططات دائرية ديناميكية وجذابة بصريًا في عروض PowerPoint باستخدام مكتبة Aspose.Slides القوية لـ .NET."
"title": "كيفية إنشاء مخطط دائري في PowerPoint باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخطط دائري في PowerPoint باستخدام Aspose.Slides لـ .NET
يُعد إنشاء مخططات بيانية جذابة بصريًا أمرًا أساسيًا لعرض البيانات بفعالية. تُعد المخططات الدائرية مثالية لتوضيح أجزاء من الكل، مما يجعلها مثالية لتصور البيانات القائمة على النسب المئوية. سيرشدك هذا البرنامج التعليمي إلى كيفية إنشاء مخطط دائري ديناميكي في PowerPoint باستخدام مكتبة Aspose.Slides for .NET القوية.

## مقدمة
غالبًا ما تتطلب العروض التقديمية تمثيلات بصرية لمجموعات بيانات معقدة، وهو ما قد لا تفي به المخططات الشريطية أو الخطية التقليدية. يُعدّ المخطط الدائري أداةً متعددة الاستخدامات لعرض البيانات المئوية بفعالية وبأسلوب ووضوح. في هذا البرنامج التعليمي، سنستكشف كيف يُبسّط Aspose.Slides for .NET عملية إنشاء هذه المخططات مباشرةً داخل PowerPoint.

**ما سوف تتعلمه:**
- إعداد Aspose.Slides لـ .NET
- تعليمات خطوة بخطوة لإنشاء مخطط دائري
- إضافة السلسلة والفئات إلى الرسم البياني الخاص بك
- تكوين تسميات البيانات لتحسين الوضوح
- حفظ العرض التقديمي النهائي

دعنا نتعمق في كيفية الاستفادة من Aspose.Slides لـ .NET لتحسين العروض التقديمية الخاصة بك باستخدام مخططات الكعكة المخصصة.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- **مكتبة Aspose.Slides لـ .NET**:متوفر عبر NuGet أو التنزيل المباشر.
- **بيئة التطوير**:يوصى باستخدام Visual Studio لمشاريع .NET.
- المعرفة الأساسية بلغة C# والتعرف على بنية PowerPoint.

## إعداد Aspose.Slides لـ .NET
لبدء إنشاء المخططات البيانية، عليك أولاً تثبيت مكتبة Aspose.Slides في مشروعك. إليك عدة طرق لتثبيتها:

**استخدام .NET CLI:**

```bash
dotnet add package Aspose.Slides
```

**استخدام وحدة تحكم إدارة الحزم:**

```powershell
Install-Package Aspose.Slides
```

**من خلال واجهة مستخدم NuGet Package Manager:**
ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

بعد التثبيت، يمكنك البدء بإعداد مشروعك. إذا كنت جديدًا على Aspose.Slides، فننصحك بالحصول على ترخيص مؤقت أو نسخة تجريبية مجانية لاستكشاف كامل إمكانياته دون قيود.

### قم بتهيئة مشروعك
فيما يلي كيفية تهيئة Aspose.Slides في تطبيقك:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // إنشاء مثيل لفئة العرض التقديمي
        Presentation presentation = new Presentation();
        
        // يذهب الكود الخاص بك للتلاعب بالعرض التقديمي هنا
        
        // حفظ العرض التقديمي
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## دليل التنفيذ
### إنشاء مخطط دائري
#### ملخص
أولاً، سننشئ مخططًا دائريًا فارغًا في شريحة PowerPoint. سيكون هذا المخطط أساسًا لإضافة البيانات وتخصيص مظهرها.

**الخطوة 1: إضافة مخطط دائري**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // أضف مخططًا دائريًا إلى الشريحة الأولى في الموضع (10، 10) بحجم (500، 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // مسح السلسلة والفئات الموجودة
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // قم بتعطيل الأسطورة للحصول على مظهر أنظف
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**توضيح:**
- **إضافة مخطط**:يُدرج مخططًا دائريًا جديدًا على الشريحة.
- **الحصول على مصنف بيانات المخطط**:يوفر إمكانية الوصول إلى خلايا البيانات في الرسم البياني للتلاعب بها.

### إضافة السلاسل والفئات
#### ملخص
بعد ذلك، سنقوم بملء الرسم البياني الخاص بك ببيانات ذات معنى عن طريق إضافة السلاسل والفئات.

**الخطوة 2: إضافة سلسلة البيانات**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // إضافة سلسلة
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // تخصيص فتحة الدونات وزاوية البداية
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // إضافة الفئات
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // تنسيق تعبئة وخط نقطة البيانات
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**توضيح:**
- **يضيف**:إدراج سلسلة وفئات جديدة في الرسم البياني.
- **تعيين حجم ثقب الكعكة**:يقوم بتكوين حجم حفرة الدونات، مما يعزز من جاذبيتها البصرية.

### تكوين تسميات البيانات
#### ملخص
تُضفي تسميات البيانات سياقًا على بيانات مخططك البياني. لنُحسّن سهولة القراءة بتخصيصها.

**الخطوة 3: تخصيص تسميات البيانات**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // تخصيص تسميات البيانات
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**توضيح:**
- **تسمية بيانات الهوية**:تخصيص تسميات البيانات لتحقيق الوضوح والعرض.
- **تعيين مركز النص**، **إظهار النسبة المئوية**:تحسين قابلية قراءة الملصقات عن طريق تركيز النص وإظهار النسب المئوية.

## خاتمة
باتباع هذا الدليل، ستتعلم كيفية إنشاء مخطط دائري ديناميكي في PowerPoint باستخدام Aspose.Slides لـ .NET. تتيح لك هذه المكتبة القوية تخصيصًا شاملاً، مما يتيح لك تصميم مخططاتك بدقة لتلبية احتياجات عرضك التقديمي.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}