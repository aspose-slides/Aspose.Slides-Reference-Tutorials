---
"date": "2025-04-15"
"description": "เรียนรู้วิธีสร้างแผนภูมิคอลัมน์แบบเรียงซ้อนตามเปอร์เซ็นต์ที่ดึงดูดสายตาด้วย Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อการแสดงภาพข้อมูลที่ชัดเจน"
"title": "วิธีการสร้างแผนภูมิคอลัมน์แบบเรียงซ้อนตามเปอร์เซ็นต์ใน .NET โดยใช้ Aspose.Slides"
"url": "/th/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการสร้างแผนภูมิคอลัมน์แบบเรียงซ้อนตามเปอร์เซ็นต์โดยใช้ Aspose.Slides สำหรับ .NET

## การแนะนำ

ในแวดวงของการแสดงภาพข้อมูล การนำเสนอข้อมูลอย่างชัดเจนและมีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับการตัดสินใจที่มีประสิทธิผล สำหรับการแสดงชุดข้อมูลที่ซับซ้อนอย่างเข้าใจง่าย แผนภูมิคอลัมน์แบบเรียงซ้อนตามเปอร์เซ็นต์ถือเป็นตัวเลือกที่เหมาะสมที่สุด คู่มือนี้จะแนะนำคุณเกี่ยวกับการสร้างแผนภูมิเหล่านี้โดยใช้ Aspose.Slides สำหรับ .NET ซึ่งเป็นไลบรารีที่มีประสิทธิภาพที่ออกแบบมาสำหรับการจัดการไฟล์การนำเสนอ

โดยทำตามบทช่วยสอนนี้ คุณจะเรียนรู้:
- การตั้งค่าข้อมูลแผนภูมิและการกำหนดรูปแบบตัวเลข
- การเพิ่มซีรีย์และปรับแต่งรูปลักษณ์ของซีรีย์
- การจัดรูปแบบฉลากเพื่อเพิ่มความสามารถในการอ่าน

พร้อมที่จะดำดิ่งลงไปหรือยัง? มาเริ่มด้วยสิ่งที่คุณต้องการก่อนเลยดีกว่า!

## ข้อกำหนดเบื้องต้น

ก่อนที่จะสร้างแผนภูมิคอลัมน์แบบเรียงซ้อนตามเปอร์เซ็นต์ โปรดตรวจสอบให้แน่ใจว่าสภาพแวดล้อมของคุณได้รับการตั้งค่าอย่างถูกต้อง คุณจะต้องมี:

### ไลบรารี เวอร์ชัน และการอ้างอิงที่จำเป็น
- **Aspose.Slides สำหรับ .NET**: ให้แน่ใจว่าได้ติดตั้งไลบรารีนี้แล้ว

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการพัฒนาที่มีการติดตั้ง .NET SDK
- Visual Studio หรือ IDE ใด ๆ ที่เข้ากันได้สำหรับการรันโค้ด C#

### ข้อกำหนดเบื้องต้นของความรู้
- ความเข้าใจพื้นฐานในการเขียนโปรแกรม C#
- ความคุ้นเคยกับการตั้งค่าโครงการ .NET และการจัดการแพ็กเกจ

## การตั้งค่า Aspose.Slides สำหรับ .NET

ในการเริ่มสร้างแผนภูมิด้วย Aspose.Slides ขั้นแรกให้ติดตั้งไลบรารีโดยใช้หนึ่งในวิธีต่อไปนี้:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**ตัวจัดการแพ็คเกจ**
```powershell
Install-Package Aspose.Slides
```

**UI ตัวจัดการแพ็กเกจ NuGet**
- ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

### ขั้นตอนการรับใบอนุญาต

เริ่มต้นด้วยการทดลองใช้ฟรีโดยดาวน์โหลดใบอนุญาตชั่วคราวจาก [เว็บไซต์ของ Aspose](https://purchase.aspose.com/temporary-license/)หากต้องการใช้ต่อ โปรดพิจารณาซื้อใบอนุญาตแบบเต็ม 

เมื่อตั้งค่าแล้ว ให้เริ่มต้น Aspose.Slides ในโปรเจ็กต์ของคุณ:
```csharp
using Aspose.Slides;
```

## คู่มือการใช้งาน

เมื่อสภาพแวดล้อมพร้อมแล้ว มาแบ่งการสร้างแผนภูมิคอลัมน์แบบเรียงซ้อนตามเปอร์เซ็นต์ออกเป็นขั้นตอนต่างๆ กัน

### การสร้างและการกำหนดค่าแผนภูมิ

#### ภาพรวม
สร้างอินสแตนซ์ของ `Presentation` ซึ่งเป็นสิ่งสำคัญสำหรับการทำงานกับสไลด์ จากนั้นเพิ่มและกำหนดค่าแผนภูมิคอลัมน์แบบเรียงซ้อนบนสไลด์ของคุณ

#### การเพิ่มแผนภูมิคอลัมน์แบบเรียงซ้อน
```csharp
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
document = new Presentation();

// รับข้อมูลอ้างอิงสไลด์แรก
slide = document.Slides[0];

// เพิ่มแผนภูมิ PercentsStackedColumn ที่ตำแหน่ง (20, 20) ด้วยขนาด (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### การกำหนดค่ารูปแบบตัวเลข
ตรวจสอบให้แน่ใจว่าข้อมูลของคุณแสดงเป็นเปอร์เซ็นต์:
```csharp
// กำหนดค่ารูปแบบตัวเลขสำหรับแกนแนวตั้ง
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // ตั้งค่ารูปแบบตัวเลขเป็นเปอร์เซ็นต์
```

#### การเพิ่มชุดข้อมูลและจุด
ล้างข้อมูลซีรีส์ที่มีอยู่และเพิ่มซีรีส์ใหม่:
```csharp
// ล้างข้อมูลซีรีส์ที่มีอยู่ทั้งหมด
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// สมุดงานข้อมูลแผนภูมิการเข้าถึง
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// เพิ่มชุดข้อมูลใหม่ "Reds"
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// ตั้งค่าสีเติมสำหรับซีรีย์เป็นสีแดง
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// กำหนดค่าคุณสมบัติรูปแบบฉลากสำหรับซีรีส์ "Reds"
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // ตั้งค่ารูปแบบเปอร์เซ็นต์
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// เพิ่มซีรีย์ "บลูส์" อีกเรื่อง
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// ตั้งค่าสีเติมสำหรับซีรีย์เป็นสีน้ำเงิน
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // ตั้งค่ารูปแบบเปอร์เซ็นต์
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### การบันทึกการนำเสนอ
บันทึกการนำเสนอของคุณลงในไฟล์:
```csharp
// บันทึกการนำเสนอในรูปแบบ PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบให้แน่ใจว่าเนมสเปซทั้งหมดได้รับการนำเข้าอย่างถูกต้อง
- ตรวจสอบการพิมพ์ผิดในชื่อคุณสมบัติและการเรียกใช้เมธอด
- ตรวจสอบว่าเส้นทางสำหรับบันทึกไฟล์ของคุณมีอยู่และมีสิทธิ์การใช้งานที่ถูกต้อง

## การประยุกต์ใช้งานจริง

ต่อไปนี้เป็นสถานการณ์บางอย่างที่แผนภูมิคอลัมน์แบบเรียงซ้อนตามเปอร์เซ็นต์อาจมีประโยชน์:
1. **การวิเคราะห์การขาย**:แสดงภาพประสิทธิภาพของผลิตภัณฑ์ในภูมิภาคต่างๆ เป็นสัดส่วนของยอดขายทั้งหมด
2. **การจัดสรรงบประมาณ**:แสดงให้เห็นว่าแผนกต่างๆ จัดสรรงบประมาณอย่างไรโดยสัมพันธ์กับการใช้จ่ายโดยรวมของบริษัท
3. **การวิจัยการตลาด**:เปรียบเทียบความต้องการของผู้บริโภคสำหรับหมวดหมู่ผลิตภัณฑ์ต่างๆ ในแต่ละช่วงเวลา
4. **ข้อมูลด้านการศึกษา**:แสดงการกระจายตัวของผลการเรียนของนักเรียนในแต่ละรายวิชา
5. **สถิติการดูแลสุขภาพ**:เป็นตัวแทนข้อมูลประชากรของผู้ป่วยในสภาวะสุขภาพต่างๆ มากมาย

## การพิจารณาประสิทธิภาพ

เพื่อประสิทธิภาพที่เหมาะสมที่สุด โปรดพิจารณา:
- จำกัดจำนวนจุดข้อมูลให้เหลือเฉพาะเท่าที่จำเป็น
- โหลดข้อมูลล่วงหน้าเพื่อลดการประมวลผลรันไทม์
- ใช้แนวทางการจัดการหน่วยความจำที่มีประสิทธิภาพด้วย Aspose.Slides สำหรับ .NET

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการสร้างแผนภูมิคอลัมน์แบบเรียงซ้อนตามเปอร์เซ็นต์โดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว เครื่องมือนี้ช่วยเพิ่มประสิทธิภาพในการนำเสนอโดยทำให้ข้อมูลที่ซับซ้อนเข้าใจได้ง่ายขึ้นและดึงดูดสายตามากขึ้น

ขั้นตอนต่อไปคืออะไร? ลองดูแผนภูมิประเภทอื่นๆ ที่มีใน Aspose.Slides หรือรวมฟังก์ชันนี้เข้ากับแอปพลิเคชันขนาดใหญ่กว่า สนุกกับการเขียนโค้ด!

## ส่วนคำถามที่พบบ่อย

**คำถามที่ 1: ฉันสามารถใช้ Aspose.Slides ได้ฟรีหรือไม่?**
A1: ใช่ คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีเพื่อทดสอบคุณสมบัติของ Aspose.Slides

**คำถามที่ 2: Aspose.Slides รองรับแผนภูมิประเภทใดบ้างสำหรับ .NET**
A2: รองรับแผนภูมิต่างๆ เช่น แผนภูมิวงกลม แผนภูมิแท่ง แผนภูมิคอลัมน์ แผนภูมิเส้น และอื่นๆ อีกมากมาย

**คำถามที่ 3: ฉันจะเริ่มต้นใช้งาน Aspose.Slides สำหรับ .NET ได้อย่างไร**
A3: ติดตั้งไลบรารีโดยใช้ NuGet หรือ .NET CLI ตามที่อธิบายไว้ข้างต้น ปฏิบัติตามเอกสารของเราเพื่อสร้างแผนภูมิแรกของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}