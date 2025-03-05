---
title: การปรับสีแผนภูมิด้วย Aspose.Slides สำหรับ .NET
linktitle: เพิ่มสีให้กับจุดข้อมูลในแผนภูมิ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มสีให้กับจุดข้อมูลในแผนภูมิด้วย Aspose.Slides สำหรับ .NET ปรับปรุงการนำเสนอของคุณด้วยภาพและดึงดูดผู้ชมของคุณอย่างมีประสิทธิภาพ
type: docs
weight: 12
url: /th/net/licensing-and-formatting/add-color-to-data-points/
---

ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการเพิ่มสีให้กับจุดข้อมูลในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีที่มีประสิทธิภาพสำหรับการทำงานกับงานนำเสนอ PowerPoint ในแอปพลิเคชัน .NET การเพิ่มสีให้กับจุดข้อมูลในแผนภูมิสามารถทำให้งานนำเสนอของคุณดูน่าดึงดูดและเข้าใจได้ง่ายขึ้น

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Visual Studio: คุณต้องติดตั้ง Visual Studio บนคอมพิวเตอร์ของคุณ

2.  Aspose.Slides สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/slides/net/).

3. ความเข้าใจพื้นฐานเกี่ยวกับ C#: คุณควรมีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

4. Your Document Directory: แทนที่ "Your Document Directory" ในโค้ดด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## การนำเข้าเนมสเปซ

ก่อนที่คุณจะทำงานกับ Aspose.Slides สำหรับ .NET ได้ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นก่อน 

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides;
```


ในตัวอย่างนี้ เราจะเพิ่มสีให้กับจุดข้อมูลในแผนภูมิโดยใช้ประเภทแผนภูมิ Sunburst

```csharp
using (Presentation pres = new Presentation())
{
    // เส้นทางไปยังไดเร็กทอรีเอกสาร
    string dataDir = "Your Document Directory";

    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Sunburst, 100, 100, 450, 400);
    
    // รหัสที่เหลือจะถูกเพิ่มในขั้นตอนต่อไปนี้
}
```

## ขั้นตอนที่ 1: การเข้าถึงจุดข้อมูล

หากต้องการเพิ่มสีให้กับจุดข้อมูลเฉพาะในแผนภูมิ คุณต้องเข้าถึงจุดข้อมูลเหล่านั้น ในตัวอย่างนี้ เราจะกำหนดเป้าหมายจุดข้อมูล 3

```csharp
IChartDataPointCollection dataPoints = chart.ChartData.Series[0].DataPoints;
dataPoints[3].DataPointLevels[0].Label.DataLabelFormat.ShowValue = true;
```

## ขั้นตอนที่ 2: การปรับแต่งป้ายกำกับข้อมูล

ตอนนี้ มาปรับแต่งป้ายกำกับข้อมูลสำหรับจุดข้อมูล 0 เราจะซ่อนชื่อหมวดหมู่และแสดงชื่อซีรีส์

```csharp
IDataLabel branch1Label = dataPoints[0].DataPointLevels[2].Label;
branch1Label.DataLabelFormat.ShowCategoryName = false;
branch1Label.DataLabelFormat.ShowSeriesName = true;
```

## ขั้นตอนที่ 3: การตั้งค่ารูปแบบข้อความและเติมสี

เราสามารถปรับปรุงลักษณะที่ปรากฏของป้ายกำกับข้อมูลเพิ่มเติมได้โดยการตั้งค่ารูปแบบข้อความและสีเติม ในขั้นตอนนี้ เราจะตั้งค่าสีข้อความเป็นสีเหลืองสำหรับจุดข้อมูล 0

```csharp
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = Color.Yellow;
```

## ขั้นตอนที่ 4: การปรับแต่งสีเติมจุดข้อมูล

ตอนนี้ เรามาเปลี่ยนสีเติมของจุดข้อมูล 9 กันดีกว่า เราจะตั้งค่าให้เป็นสีเฉพาะ

```csharp
IFormat steam4Format = dataPoints[9].Format;
steam4Format.Fill.FillType = FillType.Solid;
steam4Format.Fill.SolidFillColor.Color = Color.FromArgb(0, 176, 240, 255);
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

หลังจากปรับแต่งแผนภูมิแล้ว คุณสามารถบันทึกงานนำเสนอพร้อมกับการเปลี่ยนแปลงได้

```csharp
pres.Save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

ยินดีด้วย! คุณได้เพิ่มสีให้กับจุดข้อมูลในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว สิ่งนี้สามารถเพิ่มความดึงดูดสายตาและความชัดเจนในการนำเสนอของคุณได้อย่างมาก

## บทสรุป

การเพิ่มสีให้กับจุดข้อมูลในแผนภูมิเป็นวิธีที่มีประสิทธิภาพในการทำให้งานนำเสนอของคุณน่าสนใจและให้ข้อมูลมากขึ้น ด้วย Aspose.Slides สำหรับ .NET คุณมีเครื่องมือในการสร้างแผนภูมิที่ดึงดูดสายตาซึ่งถ่ายทอดข้อมูลของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย (FAQ)

### Aspose.Slides สำหรับ .NET คืออะไร
   Aspose.Slides สำหรับ .NET เป็นไลบรารีที่ช่วยให้นักพัฒนา .NET สามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม

### ฉันสามารถปรับแต่งคุณสมบัติแผนภูมิอื่นๆ โดยใช้ Aspose.Slides ได้หรือไม่
   ใช่ คุณสามารถปรับแต่งแง่มุมต่างๆ ของแผนภูมิได้ เช่น ป้ายข้อมูล แบบอักษร สี และอื่นๆ โดยใช้ Aspose.Slides สำหรับ .NET

### ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
    คุณสามารถดูเอกสารรายละเอียดได้ที่[ลิงค์เอกสาร](https://reference.aspose.com/slides/net/).

### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
    ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
    สำหรับการสนับสนุนและการสนทนาโปรดไปที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/).