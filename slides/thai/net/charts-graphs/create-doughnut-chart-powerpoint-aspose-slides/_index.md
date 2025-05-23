---
"date": "2025-04-15"
"description": "เรียนรู้วิธีการสร้างแผนภูมิโดนัทแบบไดนามิกและดึงดูดสายตาในงานนำเสนอ PowerPoint โดยใช้ไลบรารี Aspose.Slides สำหรับ .NET อันทรงพลัง"
"title": "วิธีการสร้างแผนภูมิโดนัทใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET"
"url": "/th/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการสร้างแผนภูมิโดนัทใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET
การสร้างแผนภูมิที่ดึงดูดสายตาถือเป็นสิ่งสำคัญสำหรับการนำเสนอข้อมูลอย่างมีประสิทธิภาพ แผนภูมิโดนัทเหมาะอย่างยิ่งสำหรับการแสดงภาพส่วนต่างๆ ของข้อมูลทั้งหมด จึงเหมาะอย่างยิ่งสำหรับการแสดงภาพข้อมูลแบบเปอร์เซ็นต์ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการสร้างแผนภูมิโดนัทแบบไดนามิกใน PowerPoint โดยใช้ไลบรารี Aspose.Slides สำหรับ .NET ที่มีประสิทธิภาพ

## การแนะนำ
การนำเสนอมักต้องการการนำเสนอข้อมูลที่ซับซ้อนในรูปแบบภาพ ซึ่งแผนภูมิแท่งหรือเส้นแบบดั้งเดิมอาจทำได้ไม่ดีนัก แผนภูมิโดนัทจึงกลายเป็นเครื่องมืออเนกประสงค์ที่ใช้สื่อสารข้อมูลตามเปอร์เซ็นต์ได้อย่างมีประสิทธิภาพด้วยสไตล์และความชัดเจน ในบทช่วยสอนนี้ เราจะมาสำรวจว่า Aspose.Slides สำหรับ .NET ช่วยลดความซับซ้อนของกระบวนการสร้างแผนภูมิเหล่านี้โดยตรงภายใน PowerPoint ได้อย่างไร

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่า Aspose.Slides สำหรับ .NET
- คำแนะนำทีละขั้นตอนในการสร้างแผนภูมิโดนัท
- การเพิ่มซีรีส์และหมวดหมู่ลงในแผนภูมิของคุณ
- การกำหนดค่าป้ายข้อมูลเพื่อความชัดเจนยิ่งขึ้น
- การบันทึกการนำเสนอขั้นสุดท้าย

มาเจาะลึกกันว่าคุณสามารถใช้ประโยชน์จาก Aspose.Slides สำหรับ .NET เพื่อปรับปรุงการนำเสนอของคุณด้วยแผนภูมิโดนัทแบบกำหนดเองได้อย่างไร

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- **Aspose.Slides สำหรับไลบรารี .NET**:พร้อมใช้งานผ่าน NuGet หรือดาวน์โหลดโดยตรง
- **สภาพแวดล้อมการพัฒนา**:ขอแนะนำ Visual Studio สำหรับโครงการ .NET
- ความรู้พื้นฐานเกี่ยวกับ C# และความคุ้นเคยกับโครงสร้างของ PowerPoint

## การตั้งค่า Aspose.Slides สำหรับ .NET
ในการเริ่มสร้างแผนภูมิ คุณต้องตั้งค่าไลบรารี Aspose.Slides ในโปรเจ็กต์ของคุณก่อน มีวิธีติดตั้งอยู่หลายวิธี:

**การใช้ .NET CLI:**

```bash
dotnet add package Aspose.Slides
```

**การใช้คอนโซลตัวจัดการแพ็คเกจ:**

```powershell
Install-Package Aspose.Slides
```

**ผ่าน UI ของตัวจัดการแพ็คเกจ NuGet:**
ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

เมื่อติดตั้งแล้ว คุณสามารถเริ่มตั้งค่าโปรเจ็กต์ของคุณได้ หากคุณเพิ่งเริ่มใช้ Aspose.Slides โปรดพิจารณาขอรับใบอนุญาตชั่วคราวหรือทดลองใช้งานฟรีเพื่อสำรวจความสามารถทั้งหมดโดยไม่มีข้อจำกัด

### เริ่มต้นโครงการของคุณ
นี่คือวิธีการเริ่มต้น Aspose.Slides ในแอปพลิเคชันของคุณ:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // สร้างอินสแตนซ์ของคลาสการนำเสนอ
        Presentation presentation = new Presentation();
        
        // โค้ดของคุณสำหรับจัดการการนำเสนออยู่ที่นี่
        
        // บันทึกการนำเสนอ
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## คู่มือการใช้งาน
### การสร้างแผนภูมิโดนัท
#### ภาพรวม
ขั้นแรก เราจะสร้างแผนภูมิโดนัทเปล่าในสไลด์ PowerPoint ซึ่งทำหน้าที่เป็นพื้นฐานสำหรับการเพิ่มข้อมูลและปรับแต่งลักษณะที่ปรากฏของข้อมูล

**ขั้นตอนที่ 1: เพิ่มแผนภูมิโดนัท**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // เพิ่มแผนภูมิโดนัทลงในสไลด์แรกที่ตำแหน่ง (10, 10) พร้อมขนาด (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // ล้างซีรีย์และหมวดหมู่ที่มีอยู่
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // ปิดใช้งานตำนานเพื่อให้ดูสะอาดขึ้น
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**คำอธิบาย:**
- **เพิ่มแผนภูมิ**: แทรกแผนภูมิโดนัทใหม่ลงบนสไลด์
- **รับChartDataWorkbook**: ให้การเข้าถึงเซลล์ข้อมูลในแผนภูมิเพื่อการจัดการ

### การเพิ่มซีรี่ส์และหมวดหมู่
#### ภาพรวม
ต่อไปเราจะเพิ่มข้อมูลที่มีความหมายลงในแผนภูมิของคุณโดยการเพิ่มชุดข้อมูลและหมวดหมู่

**ขั้นตอนที่ 2: เพิ่มชุดข้อมูล**

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

        // เพิ่มซีรี่ย์
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // การปรับแต่งรูโดนัทและมุมเริ่มต้น
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // เพิ่มหมวดหมู่
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

                // การจัดรูปแบบการเติมและเส้นของจุดข้อมูล
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

**คำอธิบาย:**
- **เพิ่ม**: แทรกชุดและหมวดหมู่ใหม่ลงในแผนภูมิ
- **ตั้งค่าขนาดรูโดนัท**:กำหนดขนาดของช่องโดนัทเพื่อเพิ่มความสวยงาม

### การกำหนดค่าป้ายข้อมูล
#### ภาพรวม
ป้ายข้อมูลช่วยให้ข้อมูลแผนภูมิของคุณมีบริบทมากขึ้น มาปรับแต่งป้ายข้อมูลให้สามารถอ่านได้ง่ายขึ้น

**ขั้นตอนที่ 3: ปรับแต่งป้ายข้อมูล**

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

                // การปรับแต่งป้ายข้อมูล
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

**คำอธิบาย:**
- **ไอดาต้าเลเบล**:ปรับแต่งป้ายข้อมูลเพื่อความชัดเจนและการนำเสนอ
- **ตั้งค่าข้อความกลาง**- **แสดงเปอร์เซ็นต์**:ปรับปรุงการอ่านฉลากโดยจัดข้อความให้ตรงกลางและแสดงเปอร์เซ็นต์

## บทสรุป
หากทำตามคำแนะนำนี้ คุณจะได้เรียนรู้วิธีสร้างแผนภูมิโดนัทแบบไดนามิกใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ไลบรารีอันทรงพลังนี้ให้คุณปรับแต่งได้มากมาย ช่วยให้คุณปรับแต่งแผนภูมิให้ตรงตามความต้องการในการนำเสนอของคุณได้อย่างแม่นยำ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}