---
title: Criar miniatura de forma de limites
linktitle: Criar miniatura de forma de limites
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar miniaturas de formas com limites usando Aspose.Slides para Java. Este tutorial passo a passo orienta você durante o processo.
weight: 10
url: /pt/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar miniatura de forma de limites

## Introdução
Aspose.Slides for Java é uma biblioteca poderosa que permite aos desenvolvedores Java criar, manipular e converter apresentações do PowerPoint programaticamente. Neste tutorial, aprenderemos como criar uma imagem em miniatura de uma forma com limites usando Aspose.Slides para Java.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Java Development Kit (JDK) instalado em seu sistema.
2.  Biblioteca Aspose.Slides para Java baixada e adicionada ao seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Importar pacotes
Certifique-se de importar os pacotes necessários em seu código Java:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Etapa 1: configure seu projeto
Crie um novo projeto Java em seu IDE preferido e adicione a biblioteca Aspose.Slides for Java às dependências do seu projeto.
## Etapa 2: instanciar um objeto de apresentação
 Instanciar um`Presentation` objeto fornecendo o caminho para o arquivo de apresentação do PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Etapa 3: criar miniatura da forma dos limites
Agora, vamos criar uma imagem em miniatura de uma forma com limites da apresentação.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Conclusão
Neste tutorial, aprendemos como criar uma imagem em miniatura de uma forma com limites usando Aspose.Slides para Java. Seguindo essas etapas, você pode gerar facilmente miniaturas de formas em suas apresentações do PowerPoint de maneira programática.
## Perguntas frequentes
### Posso criar miniaturas para formas específicas em um slide?
Sim, você pode acessar formas individuais em um slide e gerar miniaturas para elas usando Aspose.Slides for Java.
### O Aspose.Slides for Java é compatível com todas as versões de arquivos do PowerPoint?
Aspose.Slides for Java oferece suporte a vários formatos de arquivo PowerPoint, incluindo PPT, PPTX, PPS, PPSX e muito mais.
### Posso personalizar a aparência das imagens em miniatura geradas?
Sim, você pode ajustar as propriedades das imagens em miniatura, como tamanho e qualidade, de acordo com suas necessidades.
### O Aspose.Slides for Java oferece suporte a outros recursos além da geração de miniaturas?
Sim, Aspose.Slides for Java oferece ampla funcionalidade para trabalhar com apresentações em PowerPoint, incluindo manipulação de slides, extração de texto e geração de gráficos.
### Existe uma versão de teste disponível para Aspose.Slides for Java?
 Sim, você pode baixar uma versão de avaliação gratuita em[aqui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
