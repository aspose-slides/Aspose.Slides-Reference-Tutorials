---
"description": "Aspose.Slides for Java kullanarak PowerPoint'teki yerleşik özelliklere nasıl erişeceğinizi öğrenin. Bu eğitim, yazar, oluşturma tarihi ve daha fazlasını alma konusunda size rehberlik eder."
"linktitle": "PowerPoint'te Yerleşik Özelliklere Erişim"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te Yerleşik Özelliklere Erişim"
"url": "/tr/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Yerleşik Özelliklere Erişim

## giriiş
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki yerleşik özelliklere nasıl erişileceğini inceleyeceğiz. Aspose.Slides, Java geliştiricilerinin PowerPoint sunumlarıyla programatik olarak çalışmasına olanak tanıyan, özellikleri okuma ve değiştirme gibi görevleri sorunsuz bir şekilde gerçekleştiren güçlü bir kütüphanedir.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın yüklü olduğundan emin olun. Bunu şu adresten indirebilirsiniz: [Burada](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Java için Aspose.Slides: Java için Aspose.Slides'ı indirin ve yükleyin [bu bağlantı](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java projenize içe aktarmanız gerekir. Java dosyanızın başına aşağıdaki içe aktarma ifadesini ekleyin:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Adım 1: Sunum Nesnesini Ayarlayın
Çalışmak istediğiniz PowerPoint sunumunu temsil edecek Sunum nesnesini ayarlayarak başlayın. Bunu şu şekilde yapabilirsiniz:
```java
// Sunum dosyasını içeren dizine giden yol
String dataDir = "path_to_your_presentation_directory/";
// Sunum sınıfını örneklendirin
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Adım 2: Belge Özelliklerine Erişim
Presentation nesnesini ayarladıktan sonra, IDocumentProperties arayüzünü kullanarak sunumun yerleşik özelliklerine erişebilirsiniz. Çeşitli özellikleri nasıl alabileceğiniz aşağıda açıklanmıştır:
### Kategori
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Mevcut Durum
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Oluşturulma Tarihi
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Yazar
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Tanım
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Anahtar kelimeler
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Son Değiştiren
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Denetçi
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Değiştirilen Tarih
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Sunum Formatı
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Son Baskı Tarihi
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Üreticiler Arasında Paylaşılır
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Ders
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Başlık
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Çözüm
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki yerleşik özelliklere nasıl erişileceğini öğrendik. Yukarıda özetlenen adımları izleyerek yazar, oluşturma tarihi ve başlık gibi çeşitli özellikleri programatik olarak kolayca alabilirsiniz.
## SSS
### Aspose.Slides for Java'yı kullanarak bu yerleşik özellikleri değiştirebilir miyim?
Evet, bu özellikleri Aspose.Slides kullanarak değiştirebilirsiniz. Sadece IDocumentProperties arayüzü tarafından sağlanan uygun ayarlayıcı yöntemlerini kullanın.
### Aspose.Slides farklı PowerPoint sürümleriyle uyumlu mudur?
Aspose.Slides, çeşitli platformlarda uyumluluğu garanti altına alarak geniş yelpazede PowerPoint sürümlerini destekler.
### Özel özellikleri de alabilir miyim?
Evet, yerleşik özelliklerin yanı sıra Aspose.Slides for Java'yı kullanarak özel özellikleri de alabilir ve değiştirebilirsiniz.
### Aspose.Slides dokümantasyon ve destek sunuyor mu?
Evet, kapsamlı dokümanları bulabilir ve destek forumlarına erişebilirsiniz. [Aspose web sitesi](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java için deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}