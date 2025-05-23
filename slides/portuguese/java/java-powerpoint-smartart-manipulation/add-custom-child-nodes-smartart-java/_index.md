---
"description": "Aprenda a adicionar nós filhos personalizados ao SmartArt em apresentações do PowerPoint usando Java com o Aspose.Slides. Aprimore seus slides com elementos gráficos profissionais sem esforço."
"linktitle": "Adicionar nós filhos personalizados no SmartArt usando Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Adicionar nós filhos personalizados no SmartArt usando Java"
"url": "/pt/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar nós filhos personalizados no SmartArt usando Java

## Introdução
SmartArt é um recurso poderoso do PowerPoint que permite aos usuários criar gráficos com aparência profissional de forma rápida e fácil. Neste tutorial, aprenderemos como adicionar nós filhos personalizados ao SmartArt usando Java com Aspose.Slides.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Java Development Kit (JDK): certifique-se de ter o Java instalado no seu sistema.
2. Aspose.Slides para Java: Baixe e instale o Aspose.Slides para Java em [aqui](https://releases.aspose.com/slides/java/).

## Pacotes de importação
Para começar, importe os pacotes necessários no seu projeto Java:
```java
import com.aspose.slides.*;
```
## Etapa 1: Carregue a apresentação
Carregue a apresentação do PowerPoint onde você deseja adicionar nós filho personalizados ao SmartArt:
```java
String dataDir = "Your Document Directory";
// Carregue a apresentação desejada
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Etapa 2: adicionar SmartArt ao slide
Agora, vamos adicionar SmartArt ao slide:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Etapa 3: mover forma SmartArt
Mova a forma SmartArt para uma nova posição:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Etapa 4: alterar a largura da forma
Alterar a largura da forma SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Etapa 5: Alterar a altura da forma
Alterar a altura da forma SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Etapa 6: Gire a forma
Gire a forma SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Etapa 7: Salve a apresentação
Por fim, salve a apresentação modificada:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Conclusão
Neste tutorial, aprendemos como adicionar nós filhos personalizados ao SmartArt usando Java com Aspose.Slides. Seguindo esses passos, você pode aprimorar suas apresentações com gráficos personalizados, tornando-as mais envolventes e profissionais.
## Perguntas frequentes
### Posso adicionar diferentes tipos de layouts SmartArt usando o Aspose.Slides para Java?
Sim, o Aspose.Slides para Java suporta vários layouts SmartArt, permitindo que você escolha aquele que melhor se adapta às suas necessidades de apresentação.
### O Aspose.Slides para Java é compatível com diferentes versões do PowerPoint?
O Aspose.Slides para Java foi projetado para funcionar perfeitamente com diferentes versões do PowerPoint, garantindo compatibilidade e consistência entre plataformas.
### Posso personalizar a aparência das formas SmartArt programaticamente?
Com certeza! Com o Aspose.Slides para Java, você pode personalizar programaticamente a aparência, o tamanho, a cor e o layout das formas SmartArt para atender às suas preferências de design.
### Aspose.Slides para Java fornece documentação e suporte?
Sim, você pode encontrar documentação abrangente e acesso aos fóruns de suporte da comunidade no site da Aspose.
### Existe uma versão de teste disponível para o Aspose.Slides para Java?
Sim, você pode baixar uma versão de teste gratuita do Aspose.Slides para Java no site para explorar seus recursos e capacidades antes de fazer uma compra [aqui](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}