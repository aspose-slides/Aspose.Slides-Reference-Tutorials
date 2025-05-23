---
"date": "2025-04-15"
"description": "เรียนรู้วิธีปรับปรุงการนำเสนอของคุณด้วยแผนภูมิแบบกระจายโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำที่ครอบคลุมนี้เพื่อสร้างและปรับแต่งแผนภูมิอย่างมีประสิทธิภาพ"
"title": "เพิ่มแผนภูมิแบบกระจายลงในงานนำเสนอโดยใช้ Aspose.Slides .NET คำแนะนำทีละขั้นตอน"
"url": "/th/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เพิ่มแผนภูมิแบบกระจายลงในงานนำเสนอโดยใช้ Aspose.Slides .NET: คำแนะนำทีละขั้นตอน

## การแนะนำ
คุณกำลังมองหาวิธีเพิ่มประสิทธิภาพการนำเสนอของคุณโดยผสานรวมแผนภูมิแบบกระจายอย่างง่ายดายหรือไม่ ด้วยพลังของ Aspose.Slides สำหรับ .NET การสร้างและปรับแต่งแผนภูมิจึงกลายเป็นเรื่องง่าย บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการเพิ่มแผนภูมิแบบกระจายลงในสไลด์ของคุณโดยใช้ Aspose.Slides สำหรับ .NET การเชี่ยวชาญเทคนิคเหล่านี้จะช่วยให้คุณนำเสนอข้อมูลได้อย่างมีประสิทธิภาพมากขึ้นและสร้างการนำเสนอที่ดึงดูดสายตา

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่า Aspose.Slides สำหรับ .NET ในโครงการของคุณ
- การสร้างงานนำเสนอใหม่และการเข้าถึงสไลด์แรก
- การเพิ่มแผนภูมิแบบกระจายที่มีเส้นเรียบลงในสไลด์
- การล้างซีรีย์ที่มีอยู่และเพิ่มซีรีย์ใหม่ลงในแผนภูมิ
- การแก้ไขจุดข้อมูลและรูปแบบเครื่องหมายเพื่อการแสดงภาพที่ดีขึ้น
- บันทึกการนำเสนอไปยังไดเร็กทอรีที่ระบุ

มาเริ่มต้นด้วยการทบทวนข้อกำหนดเบื้องต้นกันก่อน

## ข้อกำหนดเบื้องต้น
ก่อนที่จะนำ Aspose.Slides ไปใช้กับ .NET โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- **Aspose.Slides สำหรับไลบรารี .NET**: เวอร์ชัน 23.7 ขึ้นไป.
- **สภาพแวดล้อมการพัฒนา**:Visual Studio 2019 หรือใหม่กว่าพร้อมด้วย .NET Framework 4.6.1+ หรือ .NET Core/5+
- **ความรู้พื้นฐานเกี่ยวกับ C#**: ความคุ้นเคยกับการเขียนโปรแกรมเชิงวัตถุใน C#

## การตั้งค่า Aspose.Slides สำหรับ .NET
หากต้องการเริ่มใช้ Aspose.Slides คุณจะต้องติดตั้งไลบรารีในโปรเจ็กต์ของคุณ ดังต่อไปนี้:

**การใช้ .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**การใช้คอนโซลตัวจัดการแพ็คเกจ:**
```powershell
Install-Package Aspose.Slides
```

**UI ตัวจัดการแพ็กเกจ NuGet:**
- ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

### การขอใบอนุญาต
คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีหรือสมัครใบอนุญาตชั่วคราวเพื่อสำรวจฟีเจอร์ทั้งหมด หากต้องการซื้อ ให้ทำตามขั้นตอนเหล่านี้:
1. เยี่ยม [ซื้อ Aspose.Slides](https://purchase.aspose.com/buy) เพื่อซื้อใบอนุญาตเต็มรูปแบบ
2. สำหรับใบอนุญาตชั่วคราว โปรดไปที่ [หน้าใบอนุญาตชั่วคราว](https://purchase-aspose.com/temporary-license/).

เมื่อคุณได้รับไฟล์ลิขสิทธิ์แล้ว ให้เพิ่มลงในโครงการของคุณโดยใช้:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## คู่มือการใช้งาน
เราจะแบ่งการใช้งานออกเป็นส่วนที่สมเหตุสมผลตามคุณลักษณะ

### สร้างการนำเสนอและเพิ่มสไลด์
หัวข้อนี้สาธิตวิธีสร้างงานนำเสนอและการเข้าถึงสไลด์แรก

#### ภาพรวม
เริ่มต้นด้วยการสร้างอินสแตนซ์ของ `Presentation` คลาสที่แสดงไฟล์ PowerPoint ของคุณ การเข้าถึงสไลด์ทำได้ง่ายโดยใช้โมเดลอ็อบเจ็กต์นี้

#### ขั้นตอนการดำเนินการ
**ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ**
```csharp
using Aspose.Slides;

// สร้างการนำเสนอใหม่
t Presentation pres = new Presentation();
```
โค้ดนี้จะเริ่มต้นเอกสารการนำเสนอใหม่

**ขั้นตอนที่ 2: เข้าถึงสไลด์แรก**
```csharp
// เข้าถึงสไลด์แรกในการนำเสนอ
ISlide slide = pres.Slides[0];
```
ที่นี่, `pres.Slides[0]` เข้าถึงสไลด์แรกเลย 

### เพิ่มแผนภูมิกระจายลงในสไลด์
ตอนนี้เรามาเพิ่มแผนภูมิแบบกระจายลงในการนำเสนอของคุณกัน

#### ภาพรวม
การเพิ่มแผนภูมิสามารถช่วยให้คุณแสดงข้อมูลในรูปแบบภาพในงานนำเสนอได้ Aspose.Slides ทำให้การรวมแผนภูมิประเภทต่างๆ รวมถึงแผนภูมิแบบกระจายเป็นเรื่องง่าย

#### ขั้นตอนการดำเนินการ
**ขั้นตอนที่ 1: สร้างและเพิ่มแผนภูมิแบบกระจาย**
```csharp
using Aspose.Slides.Charts;

// สร้างและเพิ่มแผนภูมิแบบกระจายเริ่มต้นด้วยเส้นเรียบ
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
สไนปเป็ตนี้จะเพิ่มแผนภูมิแบบกระจายที่ตำแหน่งและขนาดที่ระบุ

### ล้างและเพิ่มชุดข้อมูลลงในแผนภูมิ
#### ภาพรวม
คุณอาจต้องปรับแต่งแผนภูมิของคุณโดยล้างชุดข้อมูลที่มีอยู่แล้วและเพิ่มชุดข้อมูลใหม่ ส่วนนี้จะครอบคลุมฟังก์ชันการทำงานดังกล่าว

#### ขั้นตอนการดำเนินการ
**ขั้นตอนที่ 1: เข้าถึงสมุดงานข้อมูลแผนภูมิ**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// ล้างซีรีย์ที่มีอยู่ก่อนหน้านี้
chart.ChartData.Series.Clear();
```
โค้ดนี้จะล้างข้อมูลที่มีอยู่เพื่อเริ่มต้นใหม่ด้วยซีรีส์ใหม่

**ขั้นตอนที่ 2: เพิ่มซีรีย์ใหม่**
```csharp
// เพิ่มซีรีย์ใหม่ชื่อ "ซีรีย์ 1"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// เพิ่มซีรีย์อีกเรื่องชื่อ "ซีรีย์ 2"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
ขั้นตอนเหล่านี้จะเพิ่มชุดใหม่สองชุดลงในแผนภูมิ

### ปรับเปลี่ยนจุดข้อมูลและรูปแบบของเครื่องหมายชุดแรก
#### ภาพรวม
ปรับแต่งจุดข้อมูลและรูปแบบของเครื่องหมายเพื่อให้แสดงกราฟแบบกระจายได้ดีขึ้น

#### ขั้นตอนการดำเนินการ
**ขั้นตอนที่ 1: เข้าถึงและเพิ่มจุดข้อมูล**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// เพิ่มจุดข้อมูล (1, 3) และ (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**ขั้นตอนที่ 2: ปรับเปลี่ยนรูปแบบเครื่องหมาย**
```csharp
// เปลี่ยนประเภทซีรีส์และปรับเปลี่ยนรูปแบบมาร์กเกอร์
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### ปรับเปลี่ยนจุดข้อมูลและรูปแบบของเครื่องหมายชุดที่สอง
#### ภาพรวม
ในทำนองเดียวกัน ปรับแต่งซีรีย์ที่สองเพื่อให้เหมาะกับความต้องการในการนำเสนอของคุณ

#### ขั้นตอนการดำเนินการ
**ขั้นตอนที่ 1: เข้าถึงและเพิ่มจุดข้อมูลหลายจุด**
```csharp
// เข้าถึงชุดแผนภูมิที่สอง
series = chart.ChartData.Series[1];

// เพิ่มจุดข้อมูลหลายจุด
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**ขั้นตอนที่ 2: ปรับเปลี่ยนรูปแบบเครื่องหมาย**
```csharp
// การเปลี่ยนขนาดเครื่องหมายและสัญลักษณ์สำหรับซีรีส์ที่สอง
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### บันทึกการนำเสนอ
สุดท้ายให้บันทึกการนำเสนอของคุณไปยังไดเร็กทอรีที่ระบุ

#### ขั้นตอนการดำเนินการ
**ขั้นตอนที่ 1: กำหนดไดเรกทอรี**
ตรวจสอบว่าไดเรกทอรีเอาต์พุตมีอยู่ หากไม่มี ให้สร้างขึ้นใหม่:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// บันทึกการนำเสนอ
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
รหัสนี้จะบันทึกไฟล์การนำเสนอของคุณไปยังตำแหน่งที่ระบุ

## บทสรุป
ตอนนี้คุณได้เพิ่มแผนภูมิแบบกระจายลงในงานนำเสนอของคุณสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET สำรวจคุณลักษณะเพิ่มเติมและการปรับแต่งที่มีอยู่ในไลบรารีต่อไป เพื่อปรับปรุงทักษะการแสดงภาพข้อมูลของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}