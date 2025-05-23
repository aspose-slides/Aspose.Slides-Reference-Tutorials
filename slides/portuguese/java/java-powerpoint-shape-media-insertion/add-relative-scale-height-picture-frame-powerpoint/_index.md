---
"description": "Aprenda como adicionar molduras de altura de escala relativa em apresentações do PowerPoint usando o Aspose.Slides para Java, aprimorando seu conteúdo visual."
"linktitle": "Adicionar moldura de altura de escala relativa no PowerPoint"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Adicionar moldura de altura de escala relativa no PowerPoint"
"url": "/pt/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar moldura de altura de escala relativa no PowerPoint

## Introdução
Neste tutorial, você aprenderá como adicionar uma moldura de imagem com altura de escala relativa em apresentações do PowerPoint usando o Aspose.Slides para Java.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Java Development Kit (JDK) instalado no seu sistema.
2. Biblioteca Aspose.Slides para Java baixada e adicionada ao seu projeto Java.

## Pacotes de importação
Para começar, importe os pacotes necessários no seu projeto Java:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Etapa 1: Configure seu projeto
Primeiro, certifique-se de ter um diretório configurado para seu projeto e que seu ambiente Java esteja configurado corretamente.
## Etapa 2: Instanciar objeto de apresentação
Crie um novo objeto de apresentação usando Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Etapa 3: Carregar a imagem a ser adicionada
Carregue a imagem que deseja adicionar à apresentação:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Etapa 4: adicionar moldura ao slide
Adicione uma moldura de imagem a um slide na apresentação:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Etapa 5: definir largura e altura da escala relativa
Defina a largura e a altura da escala relativa para a moldura da imagem:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Etapa 6: Salvar apresentação
Salve a apresentação com a moldura adicionada:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Conclusão
Seguindo estes passos, você pode adicionar facilmente uma moldura com altura de escala relativa em apresentações do PowerPoint usando o Aspose.Slides para Java. Experimente diferentes valores de escala para obter a aparência desejada para suas imagens.

## Perguntas frequentes
### Posso adicionar vários quadros de imagem a um único slide usando este método?
Sim, você pode adicionar vários quadros de imagem a um slide repetindo o processo para cada imagem.
### O Aspose.Slides para Java é compatível com todas as versões do PowerPoint?
O Aspose.Slides para Java é compatível com várias versões do PowerPoint, garantindo flexibilidade na criação de apresentações.
### Posso personalizar a posição e o tamanho da moldura?
Com certeza, você pode ajustar os parâmetros de posição e tamanho no `addPictureFrame` método que se adapte às suas necessidades.
### O Aspose.Slides para Java suporta outros formatos de imagem além de JPEG?
Sim, o Aspose.Slides para Java suporta vários formatos de imagem, incluindo PNG, GIF, BMP e muito mais.
### Existe um fórum da comunidade ou canal de suporte disponível para usuários do Aspose.Slides?
Sim, você pode visitar o fórum Aspose.Slides para quaisquer dúvidas, discussões ou assistência relacionada à biblioteca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}