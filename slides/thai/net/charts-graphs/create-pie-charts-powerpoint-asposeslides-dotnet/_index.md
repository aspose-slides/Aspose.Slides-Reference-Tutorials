---
"date": "2025-04-15"
"description": "เรียนรู้วิธีการสร้างแผนภูมิวงกลมอัตโนมัติใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ด้วยคู่มือฉบับสมบูรณ์นี้ ปรับปรุงการนำเสนอของคุณได้อย่างง่ายดาย"
"title": "วิธีการสร้างและปรับแต่งแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET (คู่มือทีละขั้นตอน)"
"url": "/th/net/charts-graphs/create-pie-charts-powerpoint-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการสร้างและปรับแต่งแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET

## การแนะนำ
การสร้างงานนำเสนอที่น่าสนใจและมีข้อมูลมากมายถือเป็นสิ่งสำคัญสำหรับการสื่อสารที่มีประสิทธิภาพ โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับชุดข้อมูลที่ซับซ้อน การทำให้การสร้างแผนภูมิ เช่น แผนภูมิวงกลมใน PowerPoint เป็นแบบอัตโนมัติโดยใช้ .NET ช่วยประหยัดเวลาและรับรองความถูกต้องแม่นยำ คำแนะนำทีละขั้นตอนนี้สาธิตวิธีการสร้างและปรับแต่งแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ซึ่งทำให้การผสานการแสดงภาพข้อมูลแบบไดนามิกเข้ากับงานนำเสนอของคุณง่ายขึ้น

### สิ่งที่คุณจะได้เรียนรู้
- การตั้งค่า Aspose.Slides สำหรับ .NET ในโครงการของคุณ
- การสร้างอินสแตนซ์ของวัตถุการนำเสนอใหม่
- การเพิ่มและกำหนดค่าแผนภูมิวงกลมในสไลด์
- การปรับแต่งชื่อแผนภูมิ ป้ายกำกับ หมวดหมู่ และชุด
- แนวทางปฏิบัติที่ดีที่สุดในการบันทึกและส่งออกงานนำเสนอ

เริ่มต้นด้วยการตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ

## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มต้น ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

### ห้องสมุดที่จำเป็น
- **Aspose.Slides สำหรับ .NET**:ไลบรารีอันทรงพลังสำหรับทำงานกับการนำเสนอ PowerPoint ด้วยโปรแกรม ตรวจสอบให้แน่ใจว่าใช้ Aspose.Slides เวอร์ชันที่เข้ากันได้สำหรับ .NET ที่รองรับความต้องการของโครงการของคุณ

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- Visual Studio: ขอแนะนำเวอร์ชันล่าสุด แต่เวอร์ชันใหม่กว่าก็เพียงพอแล้ว
- .NET Framework หรือ .NET Core/5+/6+: ขึ้นอยู่กับสภาพแวดล้อมการพัฒนาและความต้องการแอปพลิเคชันของคุณ

### ข้อกำหนดเบื้องต้นของความรู้
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ความคุ้นเคยกับแนวคิดการเขียนโปรแกรมเชิงวัตถุ
- ประสบการณ์การทำงานกับไลบรารี .NET บางส่วนอาจเป็นประโยชน์ แต่ไม่ใช่สิ่งบังคับ

เมื่อตรวจสอบข้อกำหนดเบื้องต้นเหล่านี้แล้ว เรามาตั้งค่า Aspose.Slides สำหรับโปรเจ็กต์ของคุณกันเลย

## การตั้งค่า Aspose.Slides สำหรับ .NET
หากต้องการรวม Aspose.Slides เข้ากับแอปพลิเคชัน .NET ให้ทำตามขั้นตอนการติดตั้งเหล่านี้:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**ตัวจัดการแพ็คเกจ**
```powershell
Install-Package Aspose.Slides
```

**UI ตัวจัดการแพ็กเกจ NuGet**
ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

### การขอใบอนุญาต
Aspose.Slides เป็นผลิตภัณฑ์เชิงพาณิชย์ แต่คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีหรือขอใบอนุญาตชั่วคราวเพื่อประเมินคุณสมบัติโดยไม่มีข้อจำกัด หากต้องการใช้งานอย่างต่อเนื่อง โปรดพิจารณาซื้อการสมัครสมาชิก:
- **ทดลองใช้งานฟรี**: เริ่มต้นโดยการดาวน์โหลดจาก [หน้าเผยแพร่ของ Aspose](https://releases-aspose.com/slides/net/).
- **ใบอนุญาตชั่วคราว**: ขอผ่านทาง [ลิงค์นี้](https://purchase.aspose.com/temporary-license/) เพื่อการประเมินผลแบบขยาย
- **ซื้อ**: สำหรับการเข้าถึงแบบเต็ม กรุณาเยี่ยมชม [หน้าการซื้อ](https://purchase-aspose.com/buy).

หลังจากได้รับใบอนุญาตแล้ว ให้เริ่มต้นใบอนุญาตนั้นในแอปพลิเคชันของคุณเพื่อลบข้อจำกัดในการทดลองใช้

```csharp
// ตัวอย่างการเริ่มต้นใช้งานใบอนุญาต Aspose.Slides
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("path_to_license_file.lic");
```

## คู่มือการใช้งาน
ตอนนี้เราได้ตั้งค่าสภาพแวดล้อมของเราเรียบร้อยแล้ว เรามาเริ่มดำเนินการสร้างแผนภูมิวงกลมกันเลย

### การสร้างงานนำเสนอใหม่
เริ่มต้นด้วยการสร้างอินสแตนซ์ใหม่ของ `Presentation` คลาสซึ่งแสดงไฟล์ PowerPoint ของคุณ:

```csharp
using (Presentation presentation = new Presentation())
{
    // ส่วนที่เหลือของโค้ดของคุณจะไปที่นี่
}
```

ขั้นตอนนี้จะเริ่มการนำเสนอเปล่าที่คุณสามารถเพิ่มสไลด์และรูปร่างได้

### การเข้าถึงสไลด์
เข้าถึงสไลด์แรกเพื่อเพิ่มแผนภูมิวงกลม ซึ่งโดยทั่วไปแล้วจะเป็นสไลด์เริ่มต้นที่สร้างขึ้นพร้อมกับการนำเสนอใหม่ทุกครั้ง:

```csharp
ISlide slide = presentation.Slides[0];
```

ตอนนี้เรามาดำเนินการเพิ่มแผนภูมิวงกลมของเรากัน

### การเพิ่มแผนภูมิวงกลม
ใช้ `AddChart` วิธีการบนวัตถุสไลด์ของคุณเพื่อแทรกแผนภูมิวงกลมตามพิกัดที่ระบุ (x, y) และมิติ (ความกว้าง, ความสูง):

```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
```

### การกำหนดค่าชื่อแผนภูมิ
ตั้งชื่อแผนภูมิของคุณเพื่อให้แสดงบริบท `TextFrameForOverriding` ช่วยให้คุณสามารถปรับแต่งเนื้อหาและการจัดรูปแบบได้:

```csharp
chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
chart.ChartTitle.Height = 20;
chart.HasTitle = true;
```

การตั้งค่าเหล่านี้จะทำให้ข้อความชื่อเรื่องอยู่ตรงกลางและตั้งความสูงที่เหมาะสมเพื่อให้สามารถอ่านได้

### การตั้งค่าป้ายข้อมูล
กำหนดค่าป้ายข้อมูลเพื่อแสดงค่าภายในแผนภูมิวงกลมของคุณ ทำให้ผู้ชมเข้าใจการมีส่วนร่วมของแต่ละส่วนได้ง่ายขึ้น:

```csharp
chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
```

บรรทัดนี้จะแก้ไขชุดข้อมูลแรกเพื่อแสดงค่าของจุดข้อมูลบนชิ้นแผนภูมิโดยตรง

### การเพิ่มหมวดหมู่และซีรี่ส์
ล้างชุดข้อมูลหรือหมวดหมู่ที่มีอยู่ จากนั้นกำหนดชุดข้อมูลหรือหมวดหมู่ใหม่พร้อมกับจุดข้อมูลของคุณ:

```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// ล้างข้อมูลที่มีอยู่ก่อนหน้านี้
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();

// เพิ่มหมวดหมู่ใหม่
chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));

// เพิ่มซีรีส์ใหม่พร้อมจุดข้อมูล
IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
series.DataPoints.AddDataPointForPieSeries(fact.GetCell(0, 1, 1, 20));
series.DataPoints.AddDataPointForPieSeries(fact.GetCell(0, 2, 1, 50));
series.DataPoints.AddDataPointForPieSeries(fact.GetCell(0, 3, 1, 30));

// เพิ่มสีสันให้กับแต่ละชิ้น
series.ParentSeriesGroup.IsColorVaried = true;
```

การตั้งค่านี้ช่วยให้คุณปรับแต่งหมวดหมู่ (เช่น ไตรมาส) และจุดข้อมูลชุด (เช่น เปอร์เซ็นต์)

### การบันทึกการนำเสนอ
สุดท้าย ให้บันทึกการนำเสนอของคุณไปยังไดเร็กทอรีที่ระบุ:

```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/Pie.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```

ขั้นตอนนี้จะช่วยให้แน่ใจว่างานของคุณจะได้รับการเก็บรักษาและสามารถเข้าถึงได้เพื่อการใช้งานหรือการแชร์ในอนาคต

## การประยุกต์ใช้งานจริง
ต่อไปนี้เป็นการใช้งานจริงในการสร้างแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides:
1. **รายงานทางการเงิน**:แสดงภาพรายได้รายไตรมาสพร้อมหมวดหมู่ที่แตกต่างกันที่แสดงถึงหน่วยธุรกิจที่แตกต่างกัน
2. **การวิเคราะห์ตลาด**:แสดงการกระจายส่วนแบ่งการตลาดระหว่างคู่แข่งในประเภทผลิตภัณฑ์
3. **ผลการสำรวจ**:แสดงเปอร์เซ็นต์การตอบแบบสำรวจความคิดเห็นจากลูกค้า

แอปพลิเคชันเหล่านี้แสดงให้เห็นถึงความหลากหลายและพลังของการสร้างแผนภูมิแบบไดนามิกสำหรับสถานการณ์มืออาชีพต่างๆ

## การพิจารณาประสิทธิภาพ
เมื่อทำงานกับชุดข้อมูลขนาดใหญ่หรือการนำเสนอที่ซับซ้อน ควรพิจารณาเคล็ดลับการเพิ่มประสิทธิภาพเหล่านี้:
- จำกัดจุดข้อมูลให้เหลือเพียงข้อมูลที่จำเป็นเพื่อป้องกันความยุ่งวุ่นวาย
- นำวัตถุแผนภูมิมาใช้ซ้ำหากเป็นไปได้แทนที่จะสร้างวัตถุใหม่
- ตรวจสอบการใช้หน่วยความจำเมื่อต้องจัดการกับไฟล์การนำเสนอจำนวนมาก

การจัดการทรัพยากรที่มีประสิทธิภาพและการออกแบบที่รอบคอบสามารถปรับปรุงประสิทธิภาพและประสบการณ์ของผู้ใช้ได้อย่างมาก

## บทสรุป
ตอนนี้คุณได้เข้าใจถึงสิ่งสำคัญในการสร้างและกำหนดค่าแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET แล้ว คู่มือนี้จะแนะนำคุณเกี่ยวกับการตั้งค่าโครงการ การเพิ่มและปรับแต่งแผนภูมิ และการบันทึกงานของคุณอย่างมีประสิทธิภาพ

### ขั้นตอนต่อไป
- ทดลองใช้ประเภทแผนภูมิต่างๆ ที่มีอยู่ใน Aspose.Slides
- สำรวจการรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชันหรือบริการเว็บ
- แบ่งปันสิ่งที่คุณสร้างสรรค์เพื่อแสดงให้เห็นถึงพลังของการแสดงภาพข้อมูลอัตโนมัติ

## ส่วนคำถามที่พบบ่อย
1. **ฉันสามารถใช้ Aspose.Slides ได้ฟรีหรือไม่?**
   - ใช่ คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีได้ หากต้องการใช้งานแบบขยายเวลา ควรพิจารณาซื้อใบอนุญาต
2. **ฉันจะปรับแต่งสีแผนภูมิในแผนภูมิวงกลมได้อย่างไร**
   - ใช้ `IsColorVaried` บน `ParentSeriesGroup` เพื่อเปิดใช้งานสีชิ้นที่หลากหลาย
3. **จะเกิดอะไรขึ้นถ้าการนำเสนอของฉันช้าเมื่อต้องจัดการกับแผนภูมิจำนวนมาก?**
   - เพิ่มประสิทธิภาพโดยลดความซับซ้อนของข้อมูลและนำแผนภูมิวัตถุกลับมาใช้ใหม่หากเป็นไปได้

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}