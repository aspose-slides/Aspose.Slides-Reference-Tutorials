---
title: Adicionar coluna em caixas de texto com Aspose.Slides para Java
linktitle: Adicionar coluna em caixas de texto com Aspose.Slides para Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como adicionar colunas a caixas de texto no PowerPoint usando Aspose.Slides para Java. Aprimore suas apresentações com este guia passo a passo.
weight: 10
url: /pt/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
Neste tutorial, exploraremos como aprimorar caixas de texto adicionando colunas usando Aspose.Slides para Java. Aspose.Slides é uma poderosa biblioteca Java que permite aos desenvolvedores criar, manipular e converter apresentações do PowerPoint de forma programática sem a necessidade do Microsoft Office. Adicionar colunas às caixas de texto pode melhorar muito a legibilidade e a organização do conteúdo dos slides, tornando suas apresentações mais envolventes e profissionais.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Conhecimento básico de programação Java.
- JDK (Java Development Kit) instalado em sua máquina.
-  Aspose.Slides para biblioteca Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Importar pacotes
Para começar, você precisa importar as classes Aspose.Slides necessárias para o seu arquivo Java. Veja como você pode fazer isso:
```java
import com.aspose.slides.*;
```
## Etapa 1: inicializar a apresentação e o slide
Primeiro, crie uma nova apresentação em PowerPoint e inicialize o primeiro slide.
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // Obtenha o primeiro slide da apresentação
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Etapa 2: adicionar AutoForma (retângulo)
Em seguida, adicione uma AutoForma do tipo Retângulo ao slide.
```java
    // Adicione uma AutoForma do tipo Retângulo
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Etapa 3: adicionar TextFrame ao retângulo
Agora, adicione um TextFrame à AutoForma Retângulo e defina seu texto inicial.
```java
    // Adicione TextFrame ao retângulo
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## Etapa 4: definir o número de colunas
Especifique o número de colunas no TextFrame.
```java
    // Obtenha o formato de texto do TextFrame
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // Especifique o número de colunas no TextFrame
    format.setColumnCount(3);
```
## Etapa 5: ajustar o espaçamento das colunas
Defina o espaçamento entre colunas no TextFrame.
```java
    // Especifique o espaçamento entre colunas
    format.setColumnSpacing(10);
```
## Etapa 6: salve a apresentação
Finalmente, salve a apresentação modificada em um arquivo PowerPoint.
```java
    // Salvar apresentação criada
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Conclusão
Seguindo essas etapas, você pode adicionar facilmente colunas a caixas de texto em apresentações do PowerPoint usando Aspose.Slides para Java. Esse recurso permite aprimorar a estrutura e a legibilidade de seus slides, tornando-os mais atraentes visualmente e profissionais.
## Perguntas frequentes
### Posso adicionar mais de três colunas a uma caixa de texto?
Sim, você pode especificar qualquer número de colunas programaticamente usando Aspose.Slides.
### Aspose.Slides é compatível com Java 11?
Sim, Aspose.Slides suporta Java 11 e versões superiores.
### Como posso obter uma licença temporária do Aspose.Slides?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### O Aspose.Slides requer o Microsoft Office instalado?
Não, o Aspose.Slides não requer a instalação do Microsoft Office na máquina.
### Onde posso encontrar mais documentação sobre Aspose.Slides para Java?
 Documentação detalhada está disponível[aqui](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
