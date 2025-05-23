---
"description": "Aprenda a habilitar as propriedades recomendadas de Somente Leitura em apresentações do PowerPoint em Java usando o Aspose.Slides para Java. Siga nosso guia passo a passo com exemplos de código-fonte para aumentar a segurança das apresentações."
"linktitle": "Propriedades recomendadas somente leitura em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Propriedades recomendadas somente leitura em slides Java"
"url": "/pt/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Propriedades recomendadas somente leitura em slides Java


## Introdução à habilitação de propriedades recomendadas somente leitura em slides Java

Neste tutorial, exploraremos como habilitar as propriedades "Somente Leitura" recomendadas para apresentações do PowerPoint usando o Aspose.Slides para Java. As propriedades "Somente Leitura" recomendadas podem ser úteis quando você deseja incentivar os usuários a visualizar uma apresentação sem fazer nenhuma alteração. Essas propriedades sugerem que a apresentação deve ser aberta no modo somente leitura. Forneceremos um guia passo a passo, juntamente com o código-fonte Java, para fazer isso.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java configurada em seu projeto. Você pode baixá-la do site [Site Aspose.Slides para Java](https://products.aspose.com/slides/java/).

## Etapa 1: Crie uma nova apresentação do PowerPoint

Começaremos criando uma nova apresentação do PowerPoint usando o Aspose.Slides para Java. Se você já tem uma apresentação, pode pular esta etapa.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

No código acima, definimos o caminho para o arquivo de saída do PowerPoint e criamos um novo objeto de apresentação.

## Etapa 2: Habilitar propriedade recomendada somente leitura

Agora, vamos habilitar a propriedade Somente Leitura Recomendada para a apresentação.

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

Neste trecho de código, usamos o `getProtectionManager().setReadOnlyRecommended(true)` método para definir a propriedade Somente Leitura Recomendada para `true`. Isso garante que, quando alguém abrir a apresentação, será solicitado a abri-la no modo somente leitura.

## Etapa 3: Salve a apresentação

Por fim, salvamos a apresentação com a propriedade Somente Leitura Recomendada habilitada.

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

Neste tutorial, você aprendeu a habilitar a propriedade "Somente Leitura Recomendado" para uma apresentação do PowerPoint usando o Aspose.Slides para Java. Esse recurso pode ser útil quando você deseja restringir a edição e incentivar os espectadores a usar a apresentação no modo somente leitura. Você pode aumentar ainda mais a segurança definindo uma senha para a apresentação.

## Perguntas frequentes

### Como desabilito a propriedade Somente Leitura Recomendado?

Para desabilitar a propriedade Read-Only Recommended, basta usar o seguinte código:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Posso definir uma senha para uma apresentação recomendada somente leitura?

Sim, você pode definir uma senha para uma apresentação somente leitura recomendada usando o Aspose.Slides para Java. Você pode usar o `setPassword` Método para definir uma senha para a apresentação. Se uma senha for definida, os usuários precisarão digitá-la para abrir a apresentação, mesmo no modo somente leitura.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Lembre-se de substituir `"YourPassword"` com a senha desejada.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}