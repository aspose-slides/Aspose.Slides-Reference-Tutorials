---
title: การใช้ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Aspose.Slides .NET
linktitle: ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูล
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับปรุงแผนภูมิ PowerPoint ของคุณโดยใช้ Aspose.Slides สำหรับ .NET ปรับแต่งเครื่องหมายจุดข้อมูลด้วยรูปภาพ สร้างการนำเสนอที่น่าสนใจ
weight: 11
url: /th/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การใช้ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Aspose.Slides .NET


เมื่อทำงานกับการนำเสนอและการแสดงภาพข้อมูล Aspose.Slides สำหรับ .NET นำเสนอคุณสมบัติอันทรงพลังมากมายเพื่อสร้าง ปรับแต่ง และจัดการแผนภูมิ ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลเพื่อปรับปรุงการนำเสนอแผนภูมิของคุณ คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการ โดยเริ่มจากข้อกำหนดเบื้องต้นและการนำเข้าเนมสเปซ ไปจนถึงการแยกย่อยแต่ละตัวอย่างออกเป็นหลายขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกในการใช้ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูล ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/slides/net/).

- การนำเสนอตัวอย่าง: สำหรับบทช่วยสอนนี้ เราจะใช้การนำเสนอตัวอย่างชื่อ "Test.pptx" คุณควรมีการนำเสนอนี้ในไดเร็กทอรีเอกสารของคุณ

ตอนนี้ เรามาเริ่มด้วยการนำเข้าเนมสเปซที่จำเป็นกัน

## นำเข้าเนมสเปซ

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

เราได้นำเข้าเนมสเปซที่จำเป็นและเริ่มต้นการนำเสนอของเราแล้ว ตอนนี้ เรามาดำเนินการใช้ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลกันดีกว่า

## ขั้นตอนที่ 1: การสร้างแผนภูมิเริ่มต้น

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//การสร้างแผนภูมิเริ่มต้น
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

เราสร้างแผนภูมิเริ่มต้นประเภท "LineWithMarkers" บนสไลด์ในตำแหน่งและขนาดที่ระบุ

## ขั้นตอนที่ 2: รับดัชนีแผ่นงานข้อมูลแผนภูมิเริ่มต้น

```csharp
// รับดัชนีแผ่นงานข้อมูลแผนภูมิเริ่มต้น
int defaultWorksheetIndex = 0;
```

ที่นี่ เราได้รับดัชนีของแผ่นงานข้อมูลแผนภูมิเริ่มต้น

## ขั้นตอนที่ 3: รับแผ่นงานข้อมูลแผนภูมิ

```csharp
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

เราดึงสมุดงานข้อมูลแผนภูมิมาเพื่อทำงานกับข้อมูลแผนภูมิ

## ขั้นตอนที่ 4: การแก้ไขซีรี่ส์แผนภูมิ

```csharp
// ลบชุดสาธิต
chart.ChartData.Series.Clear();

// เพิ่มซีรีส์ใหม่
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

ในขั้นตอนนี้ เราจะลบซีรีส์สาธิตที่มีอยู่ออก และเพิ่มซีรีส์ใหม่ชื่อ "ซีรีส์ 1" ลงในแผนภูมิ

## ขั้นตอนที่ 5: การตั้งค่าการเติมรูปภาพสำหรับจุดข้อมูล

```csharp
// ตั้งค่ารูปภาพสำหรับเครื่องหมาย
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// ใช้แผนภูมิชุดแรก
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

เราตั้งค่าเครื่องหมายรูปภาพสำหรับจุดข้อมูล ซึ่งช่วยให้คุณปรับแต่งลักษณะการแสดงจุดข้อมูลแต่ละจุดบนแผนภูมิได้

## ขั้นตอนที่ 6: การเปลี่ยนขนาดเครื่องหมายชุดแผนภูมิ

```csharp
// การเปลี่ยนขนาดเครื่องหมายชุดแผนภูมิ
series.Marker.Size = 15;
```

ที่นี่ เราจะปรับขนาดของเครื่องหมายชุดแผนภูมิเพื่อให้ดูน่าดึงดูด

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

สุดท้ายนี้ เราจะบันทึกงานนำเสนอด้วยการตั้งค่าแผนภูมิใหม่

## บทสรุป

Aspose.Slides สำหรับ .NET ช่วยให้คุณสร้างการนำเสนอแผนภูมิที่น่าทึ่งด้วยตัวเลือกการปรับแต่งที่หลากหลาย ในบทช่วยสอนนี้ เรามุ่งเน้นไปที่การใช้ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลเพื่อปรับปรุงการแสดงข้อมูลของคุณด้วยภาพ ด้วย Aspose.Slides สำหรับ .NET คุณสามารถยกระดับการนำเสนอของคุณไปอีกระดับ ทำให้น่าสนใจและให้ข้อมูลมากขึ้น

หากคุณมีคำถามหรือต้องการความช่วยเหลือเกี่ยวกับ Aspose.Slides สำหรับ .NET โปรดไปที่[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/net/) หรือติดต่อได้ที่[กำหนดชุมชน](https://forum.aspose.com/) สำหรับการสนับสนุน

## คำถามที่พบบ่อย (FAQ)

### ฉันสามารถใช้รูปภาพที่กำหนดเองเป็นตัวทำเครื่องหมายสำหรับจุดข้อมูลใน Aspose.Slides สำหรับ .NET ได้หรือไม่
ได้ คุณสามารถใช้รูปภาพแบบกำหนดเองเป็นตัวทำเครื่องหมายสำหรับจุดข้อมูลใน Aspose.Slides สำหรับ .NET ดังที่แสดงในบทช่วยสอนนี้

### ฉันจะเปลี่ยนประเภทแผนภูมิใน Aspose.Slides สำหรับ .NET ได้อย่างไร
 คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการระบุประเภทอื่น`ChartType` เมื่อสร้างแผนภูมิ เช่น "แท่ง" "พาย" หรือ "พื้นที่"

### Aspose.Slides สำหรับ .NET เข้ากันได้กับ PowerPoint เวอร์ชันล่าสุดหรือไม่
Aspose.Slides สำหรับ .NET ได้รับการออกแบบมาเพื่อทำงานกับรูปแบบ PowerPoint ต่างๆ และได้รับการอัปเดตเป็นประจำเพื่อรักษาความเข้ากันได้กับ PowerPoint เวอร์ชันล่าสุด

### ฉันจะหาบทช่วยสอนและทรัพยากรเพิ่มเติมสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถสำรวจบทช่วยสอนและทรัพยากรเพิ่มเติมได้ใน[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/net/).

### มี Aspose.Slides สำหรับ .NET เวอร์ชันทดลองใช้งานหรือไม่
 ได้ คุณสามารถลองใช้ Aspose.Slides สำหรับ .NET ได้โดยดาวน์โหลดเวอร์ชันทดลองใช้ฟรีจาก[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
