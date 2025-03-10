---
title: แปลงการนำเสนอเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่
linktitle: แปลงการนำเสนอเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีใช้ Aspose.Slides สำหรับ .NET เพื่อแปลงงานนำเสนอเป็น PDF ด้วยสไลด์ที่ซ่อนไว้ได้อย่างราบรื่น
weight: 26
url: /th/net/presentation-conversion/convert-presentation-to-pdf-with-hidden-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงการนำเสนอเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่


## ข้อมูลเบื้องต้นเกี่ยวกับ Aspose.Slides สำหรับ .NET

Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งมีคุณสมบัติที่ครอบคลุมสำหรับการทำงานกับงานนำเสนอในแอปพลิเคชัน .NET ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข จัดการ และแปลงงานนำเสนอเป็นรูปแบบต่างๆ รวมถึง PDF

## ทำความเข้าใจกับสไลด์ที่ซ่อนอยู่ในการนำเสนอ

สไลด์ที่ซ่อนคือสไลด์ภายในงานนำเสนอที่ไม่สามารถมองเห็นได้ในระหว่างการนำเสนอสไลด์ปกติ อาจมีข้อมูลเสริม เนื้อหาสำรอง หรือเนื้อหาที่มีไว้สำหรับผู้ชมเฉพาะกลุ่ม เมื่อแปลงงานนำเสนอเป็น PDF จำเป็นอย่างยิ่งที่จะต้องแน่ใจว่ารวมสไลด์ที่ซ่อนไว้เหล่านี้ไว้ด้วยเพื่อรักษาความสมบูรณ์ของงานนำเสนอ

## การตั้งค่าสภาพแวดล้อมการพัฒนา

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET ใด ๆ
-  Aspose.Slides สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/net).

## กำลังโหลดไฟล์นำเสนอ

ในการเริ่มต้น มาโหลดไฟล์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET:

```csharp
using Aspose.Slides;

// โหลดงานนำเสนอ
using var presentation = new Presentation("sample.pptx");
```

## การแปลงงานนำเสนอเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่

ตอนนี้เราสามารถระบุสไลด์ที่ซ่อนได้แล้ว เรามาแปลงงานนำเสนอเป็น PDF ต่อไปโดยตรวจสอบให้แน่ใจว่าได้รวมสไลด์ที่ซ่อนไว้แล้ว:

```csharp
var pdfOptions = new PdfOptions();
pdfOptions.ShowHiddenSlides = true; // รวมสไลด์ที่ซ่อนอยู่ในรูปแบบ PDF

presentation.Save("output.pdf", SaveFormat.Pdf, pdfOptions);
```

## ตัวเลือกและการปรับแต่งเพิ่มเติม

Aspose.Slides สำหรับ .NET มีตัวเลือกและการปรับแต่งที่หลากหลายสำหรับกระบวนการแปลง คุณสามารถตั้งค่าตัวเลือกเฉพาะ PDF ได้ เช่น ขนาดหน้า การวางแนว และคุณภาพ เพื่อปรับผลลัพธ์ PDF ให้เหมาะสม

## ตัวอย่างโค้ด: แปลงการนำเสนอเป็น PDF พร้อมสไลด์ที่ซ่อนอยู่

ต่อไปนี้เป็นตัวอย่างที่สมบูรณ์ของการแปลงงานนำเสนอเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่โดยใช้ Aspose.Slides สำหรับ .NET:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        using var presentation = new Presentation("sample.pptx");

        var pdfOptions = new PdfOptions();
        pdfOptions.ShowHiddenSlides = true;

        presentation.Save("output.pdf", SaveFormat.Pdf, pdfOptions);
    }
}
```

## บทสรุป

การแปลงงานนำเสนอเป็น PDF เป็นงานทั่วไป แต่เมื่อต้องจัดการกับสไลด์ที่ซ่อนอยู่ สิ่งสำคัญคือต้องใช้ไลบรารีที่เชื่อถือได้ เช่น Aspose.Slides สำหรับ .NET ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณสามารถแปลงงานนำเสนอเป็น PDF ได้อย่างราบรื่น ในขณะเดียวกันก็รับประกันว่าจะมีสไลด์ที่ซ่อนไว้รวมอยู่ด้วย โดยจะรักษาคุณภาพโดยรวมและบริบทของงานนำเสนอ

## คำถามที่พบบ่อย

### ฉันจะรวมสไลด์ที่ซ่อนอยู่ใน PDF โดยใช้ Aspose.Slides สำหรับ .NET ได้อย่างไร

 หากต้องการรวมสไลด์ที่ซ่อนอยู่ในการแปลง PDF คุณสามารถตั้งค่า`ShowHiddenSlides` ทรัพย์สินเพื่อ`true` ในตัวเลือก PDF ก่อนที่จะบันทึกงานนำเสนอเป็น PDF

### ฉันสามารถปรับแต่งการตั้งค่าเอาต์พุต PDF โดยใช้ Aspose.Slides ได้หรือไม่

ใช่ Aspose.Slides สำหรับ .NET มีตัวเลือกมากมายในการปรับแต่งการตั้งค่าเอาต์พุต PDF เช่น ขนาดหน้า การวางแนว และคุณภาพของภาพ

### Aspose.Slides สำหรับ .NET เหมาะสำหรับการนำเสนอทั้งแบบง่ายและซับซ้อนหรือไม่

แน่นอนว่า Aspose.Slides สำหรับ .NET ได้รับการออกแบบมาเพื่อรองรับการนำเสนอที่มีความซับซ้อนแตกต่างกัน เหมาะสำหรับงานแปลงการนำเสนอทั้งแบบง่ายและซับซ้อน

### ฉันจะดาวน์โหลดไลบรารี Aspose.Slides สำหรับ .NET ได้ที่ไหน

 คุณสามารถดาวน์โหลดไลบรารี Aspose.Slides สำหรับ .NET ได้จาก[ที่นี่](https://releases.aspose.com/slides/net).

### มีเอกสารประกอบสำหรับ Aspose.Slides สำหรับ .NET หรือไม่

 ใช่ คุณสามารถค้นหาเอกสารประกอบและตัวอย่างการใช้งานสำหรับ Aspose.Slides สำหรับ .NET ได้ที่[ที่นี่](https://reference.aspose.com/slides/net).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
