---
title: เข้าถึงความคิดเห็นของสไลด์โดยใช้ Aspose.Slides
linktitle: เข้าถึงความคิดเห็นของสไลด์
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีการเข้าถึงความคิดเห็นของสไลด์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปรับปรุงการทำงานร่วมกันและขั้นตอนการทำงานได้อย่างง่ายดาย
weight: 11
url: /th/net/slide-comments-manipulation/access-slide-comments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เข้าถึงความคิดเห็นของสไลด์โดยใช้ Aspose.Slides


ในโลกของการนำเสนอแบบไดนามิกและการโต้ตอบ การจัดการความคิดเห็นภายในสไลด์ของคุณอาจเป็นส่วนสำคัญของกระบวนการทำงานร่วมกัน Aspose.Slides สำหรับ .NET มอบโซลูชันที่แข็งแกร่งและอเนกประสงค์ในการเข้าถึงและจัดการความคิดเห็นของสไลด์ ซึ่งช่วยปรับปรุงขั้นตอนการนำเสนอของคุณ ในคำแนะนำทีละขั้นตอนนี้ เราจะเจาะลึกกระบวนการเข้าถึงความคิดเห็นเกี่ยวกับสไลด์โดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

### 1. Aspose.Slides สำหรับ .NET

คุณต้องติดตั้ง Aspose.Slides สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ดำเนินการ คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/slides/net/).

### 2. เลื่อนความคิดเห็นในการนำเสนอของคุณ

ตรวจสอบให้แน่ใจว่าคุณมีงานนำเสนอ PowerPoint พร้อมความคิดเห็นเกี่ยวกับสไลด์ที่คุณต้องการเข้าถึง คุณสามารถสร้างข้อคิดเห็นเหล่านี้ใน PowerPoint หรือเครื่องมืออื่นๆ ที่รองรับข้อคิดเห็นของสไลด์

## นำเข้าเนมสเปซ

หากต้องการทำงานกับ Aspose.Slides สำหรับ .NET และเข้าถึงความคิดเห็นเกี่ยวกับสไลด์ คุณจะต้องนำเข้าเนมสเปซที่จำเป็น ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

### ขั้นตอนที่ 1: นำเข้าเนมสเปซ

ขั้นแรก เปิดตัวแก้ไขโค้ด C# ของคุณและรวมเนมสเปซที่จำเป็นไว้ที่ด้านบนของไฟล์โค้ดของคุณ:

```csharp
using Aspose.Slides;
using Aspose.Slides.Comment;
using System;
```

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นและนำเข้าเนมสเปซที่จำเป็นแล้ว เรามาเจาะลึกกระบวนการทีละขั้นตอนในการเข้าถึงความคิดเห็นเกี่ยวกับสไลด์โดยใช้ Aspose.Slides สำหรับ .NET กัน

## ขั้นตอนที่ 2: ตั้งค่าไดเร็กทอรีเอกสาร

 กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณซึ่งมีการนำเสนอ PowerPoint พร้อมความคิดเห็นเกี่ยวกับสไลด์อยู่ แทนที่`"Your Document Directory"` ด้วยเส้นทางที่แท้จริง:

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของชั้นเรียนการนำเสนอ

ตอนนี้เรามาสร้างอินสแตนซ์ของ`Presentation` ซึ่งจะช่วยให้คุณสามารถทำงานกับงานนำเสนอ PowerPoint ของคุณได้:

```csharp
using (Presentation presentation = new Presentation(dataDir + "YourPresentation.pptx"))
{
    // รหัสของคุณจะไปที่นี่
}
```

## ขั้นตอนที่ 4: ทำซ้ำผ่านผู้เขียนความคิดเห็น

ในขั้นตอนนี้ เราจะวนซ้ำผู้เขียนความคิดเห็นในงานนำเสนอของคุณ ผู้เขียนความคิดเห็นคือบุคคลที่เพิ่มความคิดเห็นลงในสไลด์:

```csharp
foreach (var commentAuthor in presentation.CommentAuthors)
{
    var author = (CommentAuthor)commentAuthor;
    
    // รหัสของคุณจะไปที่นี่
}
```

## ขั้นตอนที่ 5: เข้าถึงความคิดเห็น

ภายในผู้เขียนความคิดเห็นแต่ละคน เราสามารถเข้าถึงความคิดเห็นได้ด้วยตนเอง ความคิดเห็นจะเชื่อมโยงกับสไลด์ที่เฉพาะเจาะจง และเราสามารถแยกข้อมูลเกี่ยวกับความคิดเห็นได้ เช่น ข้อความ ผู้แต่ง และเวลาในการสร้าง:

```csharp
foreach (var commentAuthor in presentation.CommentAuthors)
{
    var author = (CommentAuthor)commentAuthor;
    
    foreach (var comment1 in author.Comments)
    {
        var comment = (Comment)comment1;
        Console.WriteLine("Slide #" + comment.Slide.SlideNumber + " has the following comment:");
        Console.WriteLine("Comment Text: " + comment.Text);
        Console.WriteLine("Author: " + comment.Author.Name);
        Console.WriteLine("Posted on: " + comment.CreatedTime + "\n");
    }
}
```

ยินดีด้วย! คุณเข้าถึงความคิดเห็นเกี่ยวกับสไลด์ในงานนำเสนอ PowerPoint ของคุณได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET เครื่องมืออันทรงพลังนี้เปิดโลกแห่งความเป็นไปได้ในการจัดการและทำงานร่วมกันในการนำเสนอของคุณ

## บทสรุป

Aspose.Slides สำหรับ .NET มอบวิธีที่ราบรื่นในการเข้าถึงและจัดการความคิดเห็นของสไลด์ในงานนำเสนอ PowerPoint ของคุณ ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณสามารถดึงข้อมูลอันมีค่าจากสไลด์ของคุณได้อย่างมีประสิทธิภาพ และปรับปรุงการทำงานร่วมกันและขั้นตอนการทำงานของคุณ

### คำถามที่พบบ่อย (FAQ)

### Aspose.Slides สำหรับ .NET คืออะไร
Aspose.Slides สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม มีคุณสมบัติมากมายสำหรับการสร้าง การแก้ไข และการจัดการไฟล์ PowerPoint

### ฉันสามารถใช้ Aspose.Slides สำหรับ .NET ในแอปพลิเคชัน .NET ต่างๆ ได้หรือไม่
ได้ Aspose.Slides สำหรับ .NET สามารถใช้ในแอปพลิเคชัน .NET ต่างๆ รวมถึง Windows Forms, ASP.NET และแอปพลิเคชันคอนโซล

### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/)- เวอร์ชันทดลองใช้งานนี้จะช่วยให้คุณสามารถสำรวจความสามารถของไลบรารีได้

### ฉันจะหาเอกสารและการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถเข้าถึงเอกสารได้ที่[Reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/) และขอการสนับสนุนในเรื่อง[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/).

### ฉันสามารถซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่
 ใช่ คุณสามารถซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET ได้จาก[ลิงค์นี้](https://purchase.aspose.com/buy) เพื่อปลดล็อกศักยภาพของห้องสมุดในโครงการของคุณอย่างเต็มที่
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
