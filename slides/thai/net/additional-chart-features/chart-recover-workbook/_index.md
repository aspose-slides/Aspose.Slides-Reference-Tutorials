---
title: วิธีใช้ Aspose.Slides .NET เพื่อกู้คืนสมุดงานจากแผนภูมิ
linktitle: กู้คืนสมุดงานจากแผนภูมิ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีการกู้คืนสมุดงานจากแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อดึงข้อมูลอย่างมีประสิทธิภาพ
weight: 12
url: /th/net/additional-chart-features/chart-recover-workbook/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ Aspose.Slides .NET เพื่อกู้คืนสมุดงานจากแผนภูมิ


หากคุณต้องการทำงานกับงานนำเสนอ PowerPoint ใน .NET Aspose.Slides สำหรับ .NET เป็นไลบรารีที่ทรงพลังที่สามารถช่วยให้คุณบรรลุเป้าหมายได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการกู้คืนสมุดงานจากแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET คุณสมบัติอันทรงพลังนี้จะมีประโยชน์เมื่อคุณต้องการดึงข้อมูลจากแผนภูมิภายในงานนำเสนอของคุณ เราจะแบ่งกระบวนการออกเป็นขั้นตอนที่ปฏิบัติตามได้ง่าย เพื่อให้มั่นใจว่าคุณมีความเข้าใจที่ชัดเจนเกี่ยวกับวิธีการทำงานนี้ให้สำเร็จ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

### 1. Aspose.Slides สำหรับ .NET

คุณควรติดตั้ง Aspose.Slides สำหรับ .NET และตั้งค่าในสภาพแวดล้อมการพัฒนา .NET ของคุณ หากคุณยังไม่มี คุณสามารถดาวน์โหลดและติดตั้งได้จากเว็บไซต์

[ดาวน์โหลด Aspose.Slides สำหรับ .NET](https://releases.aspose.com/slides/net/)

### 2. การนำเสนอด้วย PowerPoint

คุณจะต้องมีงานนำเสนอ PowerPoint พร้อมแผนภูมิที่คุณต้องการกู้คืนสมุดงาน ตรวจสอบให้แน่ใจว่าคุณมีไฟล์การนำเสนอพร้อม

## การนำเข้าเนมสเปซที่จำเป็น

ในขั้นตอนนี้ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อให้ทำงานกับ Aspose.Slides สำหรับ .NET ได้อย่างมีประสิทธิภาพ

### ขั้นตอนที่ 1: นำเข้าเนมสเปซ

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

ตอนนี้ เรามาแบ่งกระบวนการกู้คืนสมุดงานจากแผนภูมิภายในงานนำเสนอ PowerPoint ออกเป็นหลายขั้นตอน

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
```

ในขั้นตอนนี้ คุณจะต้องระบุไดเร็กทอรีซึ่งเป็นที่ตั้งของงานนำเสนอ PowerPoint ของคุณ

## ขั้นตอนที่ 2: โหลดการนำเสนอและเปิดใช้งานการกู้คืนสมุดงาน

```csharp
string pptxFile = Path.Combine(dataDir, "YourPresentation.pptx");
string outPptxFile = Path.Combine(RunExamples.OutPath, "RecoveredWorkbook.pptx");

LoadOptions lo = new LoadOptions();
lo.SpreadsheetOptions.RecoverWorkbookFromChartCache = true;

using (Presentation pres = new Presentation(pptxFile, lo))
{
    // รหัสของคุณสำหรับการกู้คืนแผนภูมิอยู่ที่นี่
    pres.Save(outPptxFile, SaveFormat.Pptx);
}
```

ในขั้นตอนนี้ คุณจะโหลดงานนำเสนอ PowerPoint จากไฟล์ที่ระบุ และเปิดใช้งานการกู้คืนสมุดงานจากแคชแผนภูมิ ที่`LoadOptions` วัตถุถูกใช้เพื่อจุดประสงค์นี้

## ขั้นตอนที่ 3: เข้าถึงและทำงานกับข้อมูลแผนภูมิ

```csharp
IChart chart = pres.Slides[0].Shapes[0] as IChart;
IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;
```

ในขั้นตอนนี้ คุณจะเข้าถึงแผนภูมิในสไลด์แรกและรับสมุดงานข้อมูลแผนภูมิ ตอนนี้คุณสามารถทำงานกับข้อมูลเวิร์กบุ๊กได้ตามต้องการ

## บทสรุป

ในบทช่วยสอนนี้ เราได้สาธิตวิธีใช้ Aspose.Slides สำหรับ .NET เพื่อกู้คืนเวิร์กบุ๊กจากแผนภูมิในงานนำเสนอ PowerPoint ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณสามารถดึงข้อมูลจากงานนำเสนอของคุณได้อย่างมีประสิทธิภาพ และนำไปใช้ตามความต้องการเฉพาะของคุณ

 หากคุณมีคำถามหรือพบปัญหาใดๆ อย่าลังเลที่จะขอความช่วยเหลือจากชุมชน Aspose.Slides ใน[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/)- พวกเขาพร้อมให้ความช่วยเหลือคุณในการเดินทางด้วย Aspose.Slides สำหรับ .NET

## คำถามที่พบบ่อย

### 1. Aspose.Slides สำหรับ .NET คืออะไร

Aspose.Slides สำหรับ .NET เป็นไลบรารี .NET ที่มีประสิทธิภาพสำหรับการทำงานกับไฟล์ Microsoft PowerPoint ซึ่งช่วยให้คุณสร้าง จัดการ และแปลงงานนำเสนอโดยทางโปรแกรมได้

### 2. ฉันสามารถลองใช้ Aspose.Slides สำหรับ .NET ก่อนซื้อได้หรือไม่

 ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ฟรีเพื่อประเมินคุณสมบัติและความสามารถของมัน[รับการทดลองใช้ฟรีที่นี่](https://releases.aspose.com/).

### 3. ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน

 คุณสามารถเข้าถึงเอกสารประกอบสำหรับ Aspose.Slides สำหรับ .NET[ที่นี่](https://reference.aspose.com/slides/net/)- ประกอบด้วยข้อมูลโดยละเอียด ตัวอย่าง และการอ้างอิง API

### 4. ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร

 หากต้องการซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET โปรดไปที่เว็บไซต์ Aspose และใช้ลิงก์ต่อไปนี้:[ซื้อ Aspose.Slides สำหรับ .NET](https://purchase.aspose.com/buy).

### 5. ความยาวสูงสุดของชื่อสำหรับการเพิ่มประสิทธิภาพ SEO คือเท่าใด?

สำหรับการเพิ่มประสิทธิภาพ SEO ขอแนะนำให้ตั้งชื่อหัวข้อให้มีความยาวไม่เกิน 60 ตัวอักษรเพื่อให้แน่ใจว่าชื่อเรื่องจะแสดงอย่างถูกต้องในผลลัพธ์ของเครื่องมือค้นหา
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
