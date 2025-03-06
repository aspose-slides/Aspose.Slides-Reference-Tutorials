---
title: ล้างจุดข้อมูลชุดแผนภูมิเฉพาะด้วย Aspose.Slides .NET
linktitle: ล้างจุดข้อมูลชุดแผนภูมิเฉพาะ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีล้างจุดข้อมูลชุดแผนภูมิเฉพาะในงานนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอน
weight: 13
url: /th/net/additional-chart-features/clear-specific-chart-series-data-points-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้คุณทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรมได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการล้างจุดข้อมูลชุดแผนภูมิเฉพาะในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถจัดการจุดข้อมูลแผนภูมิได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม คุณจะต้องแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Slides สำหรับ .NET Library: คุณควรติดตั้ง Aspose.Slides สำหรับ .NET Library คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).

2. สภาพแวดล้อมการพัฒนา: คุณควรมีสภาพแวดล้อมการพัฒนาที่ตั้งค่าด้วย Visual Studio หรือเครื่องมือพัฒนา .NET อื่น ๆ

ตอนนี้คุณมีข้อกำหนดเบื้องต้นพร้อมแล้ว เรามาเจาะลึกคำแนะนำทีละขั้นตอนเพื่อล้างจุดข้อมูลชุดแผนภูมิเฉพาะโดยใช้ Aspose.Slides สำหรับ .NET

## นำเข้าเนมสเปซ

ในโค้ด C# ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

 ขั้นแรก คุณต้องโหลดงานนำเสนอ PowerPoint ที่มีแผนภูมิที่คุณต้องการใช้งาน แทนที่`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "TestChart.pptx"))
{
    // รหัสของคุณอยู่ที่นี่
}
```

## ขั้นตอนที่ 2: เข้าถึงสไลด์และแผนภูมิ

เมื่อคุณโหลดงานนำเสนอแล้ว คุณจะต้องเข้าถึงสไลด์และแผนภูมิบนสไลด์นั้น ในตัวอย่างนี้ เราถือว่าแผนภูมิอยู่บนสไลด์แรก (ดัชนี 0)

```csharp
ISlide slide = pres.Slides[0];
IChart chart = (IChart)slide.Shapes[0];
```

## ขั้นตอนที่ 3: ล้างจุดข้อมูล

ตอนนี้ เรามาวนซ้ำจุดข้อมูลในชุดแผนภูมิและล้างค่าของจุดเหล่านั้น วิธีนี้จะลบจุดข้อมูลออกจากซีรีส์อย่างมีประสิทธิภาพ

```csharp
foreach (IChartDataPoint dataPoint in chart.ChartData.Series[0].DataPoints)
{
    dataPoint.XValue.AsCell.Value = null;
    dataPoint.YValue.AsCell.Value = null;
}

chart.ChartData.Series[0].DataPoints.Clear();
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

หลังจากการล้างจุดข้อมูลชุดแผนภูมิที่เฉพาะเจาะจงแล้ว คุณควรบันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์ใหม่หรือเขียนทับต้นฉบับ ขึ้นอยู่กับความต้องการของคุณ

```csharp
pres.Save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## บทสรุป

คุณได้เรียนรู้วิธีล้างจุดข้อมูลชุดแผนภูมิเฉพาะโดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว นี่อาจเป็นฟีเจอร์ที่มีประโยชน์เมื่อคุณต้องการจัดการข้อมูลแผนภูมิในงานนำเสนอ PowerPoint ของคุณโดยทางโปรแกรม

 หากคุณมีคำถามหรือพบปัญหาใด ๆ โปรดเยี่ยมชมที่[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/) หรือขอความช่วยเหลือในการ[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/).

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Slides สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Slides ได้รับการออกแบบมาสำหรับภาษา .NET เป็นหลัก อย่างไรก็ตาม มีเวอร์ชันสำหรับ Java และแพลตฟอร์มอื่นๆ เช่นกัน

### Aspose.Slides สำหรับ .NET เป็นไลบรารีแบบชำระเงินหรือไม่
 ใช่ Aspose.Slides เป็นห้องสมุดเชิงพาณิชย์ แต่คุณสามารถสำรวจได้[ทดลองฟรี](https://releases.aspose.com/) ก่อนที่จะซื้อ

### ฉันจะเพิ่มจุดข้อมูลใหม่ลงในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET ได้อย่างไร
 คุณสามารถเพิ่มจุดข้อมูลใหม่ได้โดยการสร้างอินสแตนซ์ของ`IChartDataPoint` และเติมค่าตามที่ต้องการ

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิใน Aspose.Slides ได้หรือไม่
ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิได้โดยการปรับเปลี่ยนคุณสมบัติ เช่น สี แบบอักษร และสไตล์

### มีชุมชนหรือชุมชนนักพัฒนาสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
ใช่ คุณสามารถเข้าร่วมชุมชน Aspose บนฟอรัมเพื่อแลกเปลี่ยนความคิดเห็น คำถาม และแบ่งปันประสบการณ์ของคุณได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
