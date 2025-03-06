---
title: Aplicar sombra externa no PowerPoint com Java
linktitle: Aplicar sombra externa no PowerPoint com Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como aplicar efeito de sombra externa no PowerPoint usando Java com Aspose.Slides. Aprimore suas apresentações com profundidade e apelo visual.
weight: 13
url: /pt/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
A criação de apresentações em PowerPoint visualmente atraentes geralmente envolve a adição de vários efeitos a formas e texto. Um desses efeitos é a sombra externa, que pode destacar os elementos e adicionar profundidade aos slides. Neste tutorial, você aprenderá como aplicar um efeito de sombra externa a uma forma no PowerPoint usando Java com Aspose.Slides.
## Pré-requisitos

Antes de começar este tutorial, certifique-se de ter os seguintes pré-requisitos:

1. Kit de desenvolvimento Java (JDK): certifique-se de ter o Java instalado em seu sistema. Você pode baixar e instalar a versão mais recente do JDK no site da Oracle.

2.  Aspose.Slides para Java: Baixe e instale Aspose.Slides para Java a partir do[página de download](https://releases.aspose.com/slides/java/).

3. Ambiente de Desenvolvimento Integrado (IDE): Escolha seu IDE Java preferido, como Eclipse, IntelliJ IDEA ou NetBeans, para codificar e executar aplicativos Java.

4. Conhecimento básico de Java: A familiaridade com os fundamentos da linguagem de programação Java e conceitos orientados a objetos será benéfica para a compreensão dos exemplos de código.

## Importar pacotes

Primeiro, importe os pacotes necessários para trabalhar com Aspose.Slides e funcionalidades relacionadas em seu projeto Java:

```java
import com.aspose.slides.*;
```

Agora vamos dividir o código de exemplo em várias etapas para aplicar o efeito de sombra externa a uma forma no PowerPoint usando Java com Aspose.Slides:

## Etapa 1: configurar o ambiente do seu projeto

Crie um novo projeto Java em seu IDE preferido e adicione a biblioteca Aspose.Slides for Java ao caminho de construção do seu projeto.

## Etapa 2: inicializar o objeto de apresentação

 Crie uma instância do`Presentation` class, que representa um arquivo de apresentação do PowerPoint.

```java
Presentation presentation = new Presentation();
```

## Etapa 3: adicionar um slide e uma forma

Obtenha uma referência ao slide onde deseja adicionar a forma e, em seguida, adicione uma AutoForma (por exemplo, retângulo) ao slide.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Etapa 4: personalize a forma

Defina o tipo de preenchimento da forma como ‘NoFill’ e adicione texto à forma.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Etapa 5: personalize o texto

Acesse as propriedades de texto da forma e personalize o tamanho da fonte.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Etapa 6: ativar o efeito Sombra externa

Ative o efeito de sombra externa para a parte do texto.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Etapa 7: definir parâmetros de sombra

Defina os parâmetros para o efeito de sombra externa, como raio de desfoque, direção, distância e cor da sombra.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Passo 8: Salve a apresentação

Salve a apresentação modificada com o efeito de sombra externa aplicado à forma.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Conclusão

Parabéns! Você aplicou com êxito um efeito de sombra externa a uma forma no PowerPoint usando Java com Aspose.Slides. Experimente diferentes parâmetros para obter os efeitos visuais desejados em suas apresentações.

## Perguntas frequentes

### Posso aplicar o efeito de sombra externa a outras formas além de retângulos?
Sim, você pode aplicar o efeito de sombra externa a várias formas suportadas pelo Aspose.Slides, como círculos, triângulos e formas personalizadas.

### É possível personalizar a cor e a intensidade da sombra?
Absolutamente! Você tem controle total sobre os parâmetros de sombra, incluindo cor, raio de desfoque, direção e distância.

### Posso aplicar vários efeitos à mesma forma?
Sim, você pode combinar vários efeitos como sombra externa, sombra interna, brilho e reflexo para aprimorar o apelo visual das formas e do texto em suas apresentações.

### O Aspose.Slides suporta a aplicação de efeitos a elementos de texto?
Sim, você pode aplicar efeitos não apenas a formas, mas também a partes individuais de texto dentro de formas, proporcionando ampla flexibilidade no design de seus slides.

### Onde posso encontrar mais recursos e suporte para Aspose.Slides?
 Você pode consultar o[documentação](https://reference.aspose.com/slides/java/) para obter referências detalhadas da API e explorar o[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) para apoio e discussões da comunidade.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
