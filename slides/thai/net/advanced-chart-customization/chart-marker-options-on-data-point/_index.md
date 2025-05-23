---
"description": "เรียนรู้วิธีปรับปรุงแผนภูมิ PowerPoint ของคุณโดยใช้ Aspose.Slides สำหรับ .NET ปรับแต่งเครื่องหมายจุดข้อมูลด้วยรูปภาพ สร้างการนำเสนอที่น่าสนใจ"
"linktitle": "ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูล"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การใช้ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Aspose.Slides .NET"
"url": "/th/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การใช้ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Aspose.Slides .NET


เมื่อทำงานกับการนำเสนอและการแสดงภาพข้อมูล Aspose.Slides สำหรับ .NET นำเสนอฟีเจอร์อันทรงพลังมากมายสำหรับการสร้าง ปรับแต่ง และจัดการแผนภูมิ ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้ตัวเลือกตัวระบุแผนภูมิบนจุดข้อมูลเพื่อปรับปรุงการนำเสนอแผนภูมิของคุณ คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการ เริ่มตั้งแต่ข้อกำหนดเบื้องต้นและการนำเข้าเนมสเปซ ไปจนถึงการแบ่งตัวอย่างแต่ละตัวอย่างออกเป็นหลายขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกการใช้ตัวเลือกเครื่องหมายแผนภูมิกับจุดข้อมูล โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์](https://releases-aspose.com/slides/net/).

- ตัวอย่างการนำเสนอ: สำหรับบทช่วยสอนนี้ เราจะใช้ตัวอย่างการนำเสนอชื่อ "Test.pptx" คุณควรมีการนำเสนอนี้ในไดเร็กทอรีเอกสารของคุณ

ตอนนี้เรามาเริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นกัน

## นำเข้าเนมสเปซ

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

เราได้นำเข้าเนมสเปซที่จำเป็นและเริ่มต้นการนำเสนอของเราแล้ว ตอนนี้ เรามาดำเนินการใช้ตัวเลือกตัวระบุแผนภูมิกับจุดข้อมูลกัน

## ขั้นตอนที่ 1: การสร้างแผนภูมิเริ่มต้น

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// การสร้างแผนภูมิเริ่มต้น
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

เราสร้างแผนภูมิเริ่มต้นของประเภท "LineWithMarkers" บนสไลด์ตามตำแหน่งและขนาดที่ระบุ

## ขั้นตอนที่ 2: รับดัชนีเวิร์กชีตข้อมูลแผนภูมิเริ่มต้น

```csharp
// การรับดัชนีเวิร์กชีตข้อมูลแผนภูมิเริ่มต้น
int defaultWorksheetIndex = 0;
```

ที่นี่ เราจะได้รับดัชนีของเวิร์กชีตข้อมูลแผนภูมิเริ่มต้น

## ขั้นตอนที่ 3: การรับแผ่นงานข้อมูลแผนภูมิ

```csharp
// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

เราดึงสมุดงานข้อมูลแผนภูมิมาใช้งานกับข้อมูลแผนภูมิ

## ขั้นตอนที่ 4: การปรับเปลี่ยนชุดแผนภูมิ

```csharp
// ลบซีรีย์สาธิต
chart.ChartData.Series.Clear();

// เพิ่มซีรีย์ใหม่
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

ในขั้นตอนนี้ เราจะลบชุดสาธิตที่มีอยู่ทั้งหมดและเพิ่มชุดใหม่ชื่อ "ชุดที่ 1" ลงในแผนภูมิ

## ขั้นตอนที่ 5: ตั้งค่าการเติมภาพสำหรับจุดข้อมูล

```csharp
// ตั้งค่ารูปภาพสำหรับเครื่องหมาย
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// มาดูแผนภูมิชุดแรกกัน
IChartSeries series = chart.ChartData.Series[0];

// เพิ่มจุดข้อมูลใหม่ด้วยการเติมรูปภาพ
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

เราตั้งค่าเครื่องหมายภาพสำหรับจุดข้อมูล ทำให้คุณปรับแต่งลักษณะการแสดงจุดข้อมูลแต่ละจุดบนแผนภูมิได้

## ขั้นตอนที่ 6: การเปลี่ยนขนาดเครื่องหมายชุดแผนภูมิ

```csharp
// การเปลี่ยนแปลงขนาดเครื่องหมายชุดแผนภูมิ
series.Marker.Size = 15;
```

ที่นี่เราปรับขนาดของเครื่องหมายชุดแผนภูมิเพื่อให้ดูน่าสนใจ

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

สุดท้าย เราบันทึกการนำเสนอโดยใช้การตั้งค่าแผนภูมิใหม่

## บทสรุป

Aspose.Slides สำหรับ .NET ช่วยให้คุณสามารถสร้างการนำเสนอแผนภูมิที่สวยงามพร้อมตัวเลือกการปรับแต่งต่างๆ ในบทช่วยสอนนี้ เราเน้นที่การใช้ตัวเลือกเครื่องหมายแผนภูมิกับจุดข้อมูลเพื่อปรับปรุงการแสดงข้อมูลของคุณในรูปแบบภาพ ด้วย Aspose.Slides สำหรับ .NET คุณสามารถยกระดับการนำเสนอของคุณให้น่าสนใจและให้ข้อมูลมากขึ้น

หากคุณมีคำถามหรือต้องการความช่วยเหลือเกี่ยวกับ Aspose.Slides สำหรับ .NET โปรดเยี่ยมชม [เอกสารประกอบ Aspose.Slides](https://reference.aspose.com/slides/net/) หรือติดต่อได้ที่ [ชุมชนอาโพส](https://forum.aspose.com/) เพื่อรองรับ

## คำถามที่พบบ่อย (FAQs)

### ฉันสามารถใช้รูปภาพที่กำหนดเองเป็นเครื่องหมายสำหรับจุดข้อมูลใน Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถใช้รูปภาพที่กำหนดเองเป็นเครื่องหมายสำหรับจุดข้อมูลใน Aspose.Slides สำหรับ .NET ได้ ตามที่สาธิตในบทช่วยสอนนี้

### ฉันจะเปลี่ยนประเภทแผนภูมิใน Aspose.Slides สำหรับ .NET ได้อย่างไร
คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยระบุชนิดอื่น `ChartType` เมื่อสร้างแผนภูมิ เช่น "แท่ง" "วงกลม" หรือ "พื้นที่"

### Aspose.Slides สำหรับ .NET เข้ากันได้กับ PowerPoint เวอร์ชันล่าสุดได้หรือไม่
Aspose.Slides สำหรับ .NET ได้รับการออกแบบมาให้ทำงานกับรูปแบบ PowerPoint ต่างๆ และได้รับการอัพเดตเป็นประจำเพื่อรักษาความเข้ากันได้กับเวอร์ชัน PowerPoint ล่าสุด

### ฉันสามารถหาบทช่วยสอนและแหล่งข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
คุณสามารถสำรวจบทช่วยสอนและทรัพยากรเพิ่มเติมได้ใน [เอกสารประกอบ Aspose.Slides](https://reference-aspose.com/slides/net/).

### มี Aspose.Slides เวอร์ชันทดลองใช้งานสำหรับ .NET หรือไม่
ใช่ คุณสามารถลองใช้ Aspose.Slides สำหรับ .NET ได้โดยดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีจาก [ที่นี่](https://releases-aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}