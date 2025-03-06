---
title: Adicionar moldura de altura em escala relativa no PowerPoint
linktitle: Adicionar moldura de altura em escala relativa no PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como adicionar molduras de altura em escala relativa em apresentações do PowerPoint usando Aspose.Slides para Java, aprimorando seu conteúdo visual.
type: docs
weight: 15
url: /pt/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---
## Introdução
Neste tutorial, você aprenderá como adicionar uma moldura de imagem com altura de escala relativa em apresentações do PowerPoint usando Aspose.Slides para Java.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Java Development Kit (JDK) instalado em seu sistema.
2. Biblioteca Aspose.Slides para Java baixada e adicionada ao seu projeto Java.

## Importar pacotes
Para começar, importe os pacotes necessários em seu projeto Java:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Etapa 1: configure seu projeto
Primeiro, certifique-se de ter um diretório configurado para seu projeto e de que seu ambiente Java esteja configurado corretamente.
## Etapa 2: instanciar objeto de apresentação
Crie um novo objeto de apresentação usando Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Etapa 3: carregar a imagem a ser adicionada
Carregue a imagem que deseja adicionar à apresentação:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Etapa 4: adicionar moldura ao slide
Adicione uma moldura a um slide da apresentação:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Etapa 5: definir largura e altura da escala relativa
Defina a largura e a altura da escala relativa do porta-retratos:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Etapa 6: salvar a apresentação
Salve a apresentação com o porta-retratos adicionado:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Conclusão
Seguindo essas etapas, você pode adicionar facilmente um porta-retratos com altura de escala relativa em apresentações do PowerPoint usando Aspose.Slides para Java. Experimente diferentes valores de escala para obter a aparência desejada para suas imagens.

## Perguntas frequentes
### Posso adicionar vários porta-retratos a um único slide usando este método?
Sim, você pode adicionar vários porta-retratos a um slide repetindo o processo para cada imagem.
### O Aspose.Slides for Java é compatível com todas as versões do PowerPoint?
Aspose.Slides for Java é compatível com diversas versões do PowerPoint, garantindo flexibilidade na criação de apresentações.
### Posso personalizar a posição e o tamanho do porta-retratos?
 Com certeza, você pode ajustar os parâmetros de posição e tamanho no`addPictureFrame` método para atender às suas necessidades.
### O Aspose.Slides for Java oferece suporte a outros formatos de imagem além de JPEG?
Sim, Aspose.Slides for Java suporta vários formatos de imagem, incluindo PNG, GIF, BMP e muito mais.
### Existe um fórum da comunidade ou canal de suporte disponível para usuários do Aspose.Slides?
Sim, você pode visitar o fórum Aspose.Slides para qualquer dúvida, discussão ou assistência em relação à biblioteca.