---
"date": "2025-04-18"
"description": "Aprenda a aprimorar suas apresentações personalizando marcadores SmartArt com imagens usando o Aspose.Slides para Java. Siga este guia passo a passo para obter uma aparência profissional."
"title": "Como personalizar marcadores SmartArt com imagens usando Aspose.Slides para Java | Guia passo a passo"
"url": "/pt/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como personalizar marcadores SmartArt com imagens usando Aspose.Slides para Java

## Introdução

Criar apresentações visualmente atraentes é crucial para capturar a atenção do público e comunicar sua mensagem com eficácia. Um desafio comum na criação de slides é aprimorar marcadores em elementos gráficos SmartArt usando imagens personalizadas. Este tutorial guiará você na definição de uma imagem como formato de preenchimento de marcadores em nós SmartArt com o Aspose.Slides para Java, permitindo que você eleve suas apresentações profissionalmente.

**O que você aprenderá:**
- Configurando e usando Aspose.Slides para Java
- Personalizando marcadores com imagens em gráficos SmartArt
- Aplicações práticas desta personalização
- Solução de problemas comuns

Antes de começarmos a implementação, certifique-se de que tudo esteja pronto.

## Pré-requisitos

Para acompanhar este tutorial, certifique-se de atender aos seguintes pré-requisitos:

1. **Bibliotecas e Dependências**Você precisará da biblioteca Aspose.Slides para Java versão 25.4 ou posterior.
2. **Configuração do ambiente**:
   - Um IDE compatível como IntelliJ IDEA ou Eclipse
   - JDK 16 instalado em sua máquina
3. **Pré-requisitos de conhecimento**: Familiaridade com programação Java e estrutura básica de apresentação do PowerPoint.

## Configurando o Aspose.Slides para Java

Para começar, inclua a biblioteca Aspose.Slides em seu projeto usando um dos seguintes métodos:

### Especialista

Adicione esta dependência ao seu `pom.xml` arquivo:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Inclua isso em seu `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download direto

Alternativamente, baixe a biblioteca diretamente de [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

**Etapas de aquisição de licença**: O Aspose oferece uma licença de teste gratuita, perfeita para testar seus recursos. Você pode solicitar uma licença temporária ou comprar uma para remover as limitações de avaliação.

Para inicializar e configurar seu ambiente, crie uma instância do `Presentation` classe como mostrado:

```java
Presentation presentation = new Presentation();
```

## Guia de Implementação

Esta seção dividirá o processo em etapas gerenciáveis, explicando como alcançar a funcionalidade desejada.

### Adicionando SmartArt com preenchimento de marcadores personalizado

#### Visão geral

Começaremos adicionando uma forma SmartArt ao seu slide e personalizando seus marcadores usando um preenchimento de imagem.

#### Instruções passo a passo

**1. Inicializar objeto de apresentação**

```java
Presentation presentation = new Presentation();
```

*Propósito*: Inicializa uma nova instância de apresentação onde você adicionará os gráficos SmartArt.

**2. Adicionar forma SmartArt**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*Explicação*: Esta linha adiciona uma nova forma SmartArt ao primeiro slide na posição (x=10, y=10) com dimensões de 500x400 pixels. `VerticalPictureList` layout é usado para alinhamento vertical.

**3. Acesse e personalize o preenchimento com marcadores**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*Propósito*: Verifica se o nó tem um `BulletFillFormat` propriedade. Se for o caso, ele carrega uma imagem e a define como preenchimento para marcadores.
*Parâmetros*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: O caminho para seu arquivo de imagem.
  - `PictureFillMode.Stretch`: Garante que a imagem preencha completamente a área do marcador.

**4. Salve sua apresentação**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}