---
"description": "เรียนรู้วิธีการกู้คืนเวิร์กบุ๊กจากแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อดึงข้อมูลอย่างมีประสิทธิภาพ"
"linktitle": "กู้คืนสมุดงานจากแผนภูมิ"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "วิธีการใช้ Aspose.Slides .NET เพื่อกู้คืนสมุดงานจากแผนภูมิ"
"url": "/th/net/additional-chart-features/chart-recover-workbook/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการใช้ Aspose.Slides .NET เพื่อกู้คืนสมุดงานจากแผนภูมิ


หากคุณต้องการทำงานกับงานนำเสนอ PowerPoint ใน .NET Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่จะช่วยให้คุณบรรลุเป้าหมายได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการกู้คืนเวิร์กบุ๊กจากแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ฟีเจอร์ที่มีประสิทธิภาพนี้จะมีประโยชน์เมื่อคุณจำเป็นต้องดึงข้อมูลจากแผนภูมิภายในงานนำเสนอของคุณ เราจะแบ่งกระบวนการออกเป็นขั้นตอนที่ทำตามได้ง่าย เพื่อให้คุณเข้าใจอย่างชัดเจนว่าต้องทำอย่างไรจึงจะทำงานนี้ได้สำเร็จ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

### 1. Aspose.Slides สำหรับ .NET

คุณควรติดตั้งและตั้งค่า Aspose.Slides สำหรับ .NET ในสภาพแวดล้อมการพัฒนา .NET ของคุณ หากคุณยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดและติดตั้งได้จากเว็บไซต์

[ดาวน์โหลด Aspose.Slides สำหรับ .NET](https://releases.aspose.com/slides/net/)

### 2. การนำเสนอ PowerPoint

คุณจะต้องมีการนำเสนอ PowerPoint พร้อมแผนภูมิที่คุณต้องการกู้คืนเวิร์กบุ๊ก ตรวจสอบให้แน่ใจว่าคุณมีไฟล์การนำเสนอพร้อมแล้ว

## การนำเข้าเนมสเปซที่จำเป็น

ในขั้นตอนนี้ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Slides สำหรับ .NET ได้อย่างมีประสิทธิภาพ

### ขั้นตอนที่ 1: นำเข้าเนมสเปซ

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

ตอนนี้ มาแบ่งขั้นตอนการกู้คืนเวิร์กบุ๊กจากแผนภูมิภายในงานนำเสนอ PowerPoint ออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
```

ในขั้นตอนนี้ คุณต้องระบุไดเร็กทอรีที่เก็บงานนำเสนอ PowerPoint ของคุณ

## ขั้นตอนที่ 2: โหลดการนำเสนอและเปิดใช้งานการกู้คืนเวิร์กบุ๊ก

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

ในขั้นตอนนี้ คุณจะโหลดการนำเสนอ PowerPoint จากไฟล์ที่ระบุ และเปิดใช้งานการกู้คืนเวิร์กบุ๊กจากแคชแผนภูมิ `LoadOptions` วัตถุถูกใช้เพื่อจุดประสงค์นี้

## ขั้นตอนที่ 3: เข้าถึงและทำงานกับข้อมูลแผนภูมิ

```csharp
IChart chart = pres.Slides[0].Shapes[0] as IChart;
IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;
```

ในขั้นตอนนี้ คุณจะเข้าถึงแผนภูมิในสไลด์แรกและรับสมุดงานข้อมูลแผนภูมิ ตอนนี้คุณสามารถทำงานกับข้อมูลสมุดงานตามต้องการได้

## บทสรุป

ในบทช่วยสอนนี้ เราได้สาธิตวิธีการใช้ Aspose.Slides สำหรับ .NET เพื่อกู้คืนเวิร์กบุ๊กจากแผนภูมิในงานนำเสนอ PowerPoint โดยทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณสามารถดึงข้อมูลจากงานนำเสนอของคุณอย่างมีประสิทธิภาพและนำไปใช้เพื่อตอบสนองความต้องการเฉพาะของคุณได้

หากคุณมีคำถามหรือพบปัญหาใดๆ โปรดอย่าลังเลที่จะขอความช่วยเหลือจากชุมชน Aspose.Slides ใน [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/)พวกเขาอยู่ที่นั่นเพื่อช่วยเหลือคุณในการเดินทางของคุณกับ Aspose.Slides สำหรับ .NET

## คำถามที่พบบ่อย

### 1. Aspose.Slides สำหรับ .NET คืออะไร?

Aspose.Slides สำหรับ .NET เป็นไลบรารี .NET ที่ทรงพลังสำหรับการทำงานกับไฟล์ Microsoft PowerPoint ช่วยให้คุณสามารถสร้าง จัดการ และแปลงงานนำเสนอผ่านโปรแกรมได้

### 2. ฉันสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ก่อนซื้อได้หรือไม่

ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรี เพื่อประเมินคุณลักษณะและความสามารถของมัน [รับการทดลองใช้ฟรีได้ที่นี่](https://releases-aspose.com/).

### 3. ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน

คุณสามารถเข้าถึงเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ [ที่นี่](https://reference.aspose.com/slides/net/)ประกอบด้วยข้อมูลรายละเอียด ตัวอย่าง และการอ้างอิง API

### 4. ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร

หากต้องการซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET ให้ไปที่เว็บไซต์ Aspose และใช้ลิงก์ต่อไปนี้: [ซื้อ Aspose.Slides สำหรับ .NET](https://purchase-aspose.com/buy).

### 5. ความยาวชื่อเรื่องสูงสุดสำหรับการปรับแต่ง SEO คือเท่าไร?

เพื่อการเพิ่มประสิทธิภาพ SEO ขอแนะนำให้ชื่อเรื่องมีความยาวไม่เกิน 60 ตัวอักษรเพื่อให้แน่ใจว่าจะแสดงอย่างถูกต้องในผลการค้นหาของเครื่องมือค้นหา

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}