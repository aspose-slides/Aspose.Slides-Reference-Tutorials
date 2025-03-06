---
title: Propriedades recomendadas somente leitura em slides Java
linktitle: Propriedades recomendadas somente leitura em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como habilitar propriedades recomendadas somente leitura em apresentações Java PowerPoint usando Aspose.Slides para Java. Siga nosso guia passo a passo com exemplos de código-fonte para aumentar a segurança da apresentação.
weight: 17
url: /pt/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introdução à ativação de propriedades recomendadas somente leitura em slides Java

Neste tutorial, exploraremos como habilitar propriedades recomendadas somente leitura para apresentações do PowerPoint usando Aspose.Slides para Java. As propriedades recomendadas somente leitura podem ser úteis quando você deseja incentivar os usuários a visualizar uma apresentação sem fazer alterações. Estas propriedades sugerem que a apresentação deve ser aberta no modo somente leitura. Forneceremos a você um guia passo a passo junto com o código-fonte Java para conseguir isso.

## Pré-requisitos

 Antes de começarmos, certifique-se de ter a biblioteca Aspose.Slides para Java configurada em seu projeto. Você pode baixá-lo no[Site Aspose.Slides para Java](https://products.aspose.com/slides/java/).

## Etapa 1: crie uma nova apresentação em PowerPoint

Começaremos criando uma nova apresentação em PowerPoint usando Aspose.Slides para Java. Se você já tem uma apresentação, pode pular esta etapa.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

No código acima, definimos o caminho para o arquivo PowerPoint de saída e criamos um novo objeto de apresentação.

## Etapa 2: ativar propriedade recomendada somente leitura

Agora, vamos habilitar a propriedade Somente leitura recomendada para a apresentação.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 Neste trecho de código, usamos o`getProtectionManager().setReadOnlyRecommended(true)` método para definir a propriedade recomendada somente leitura como`true`. Isso garante que quando alguém abrir a apresentação, será solicitado a abri-la no modo somente leitura.

## Etapa 3: salve a apresentação

Por fim, salvamos a apresentação com a propriedade Somente leitura recomendada habilitada.

## Código-fonte completo para propriedades recomendadas somente leitura em slides Java

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, você aprendeu como habilitar a propriedade somente leitura recomendada para uma apresentação do PowerPoint usando Aspose.Slides para Java. Este recurso pode ser útil quando você deseja restringir a edição e incentivar os espectadores a usar a apresentação no modo somente leitura. Você pode aumentar ainda mais a segurança definindo uma senha para a apresentação.

## Perguntas frequentes

### Como desativo a propriedade Recomendada somente leitura?

Para desabilitar a propriedade somente leitura recomendada, basta usar o seguinte código:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Posso definir uma senha para uma apresentação recomendada somente leitura?

Sim, você pode definir uma senha para uma apresentação recomendada somente leitura usando Aspose.Slides para Java. Você pode usar o`setPassword` método para definir uma senha para a apresentação. Se uma senha for definida, os usuários precisarão digitá-la para abrir a apresentação, mesmo no modo somente leitura.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Lembre-se de substituir`"YourPassword"` com a senha desejada.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
