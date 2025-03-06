---
title: Como definir o clique do hiperlink de macro em Aspose.Slides para .NET
linktitle: Gerenciamento de hiperlinks usando macros
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como definir hiperlinks de macro em suas apresentações com Aspose.Slides for .NET. Aumente a interatividade e envolva seu público.
type: docs
weight: 13
url: /pt/net/hyperlink-manipulation/macro-hyperlink/
---

No mundo do desenvolvimento de software moderno, a criação de apresentações dinâmicas e interativas é um aspecto fundamental. Aspose.Slides for .NET é uma biblioteca poderosa que permite trabalhar com apresentações de maneira integrada. Esteja você criando uma apresentação de negócios ou uma apresentação de slides educacional, a capacidade de definir cliques em hiperlinks macro pode melhorar muito a experiência do usuário. Neste guia passo a passo, orientaremos você no processo de configuração de um clique de hiperlink de macro usando Aspose.Slides for .NET. 

## Pré-requisitos

Antes de mergulharmos no tutorial passo a passo, existem alguns pré-requisitos que você deve ter:

1.Visual Studio: Certifique-se de ter o Visual Studio instalado em seu computador, pois este será nosso ambiente de desenvolvimento.

 2.Aspose.Slides for .NET: Você precisará ter a biblioteca Aspose.Slides for .NET instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/net/).

3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# é essencial para acompanhar este tutorial.

## Importar namespaces

Na primeira etapa, vamos importar os namespaces necessários para trabalhar com Aspose.Slides:

### Etapa 1: importar namespaces

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Nós importamos o`Aspose.Slides` namespace, que é o namespace principal para trabalhar com apresentações, e o`Aspose.Slides.Export` espaço para nome.

## Configurando o clique do hiperlink da macro

Agora, vamos passar para a parte principal deste tutorial - definir um clique de hiperlink de macro em sua apresentação.

### Etapa 2: inicializar a apresentação

Primeiro, precisamos inicializar uma nova apresentação.

```csharp
using (Presentation presentation = new Presentation())
{
    // Seu código irá aqui.
}
```

Dentro desta instrução using, você cria um novo objeto de apresentação e executa todas as suas operações dentro dele.

### Etapa 3: adicionar uma AutoForma

Para definir um clique de hiperlink de macro, você precisará de um objeto no qual o usuário possa clicar. Neste exemplo, usaremos uma AutoForma como elemento clicável.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Aqui criamos uma AutoShape do tipo “BlankButton” em coordenadas específicas (20, 20) e com dimensões de 80x30. Você pode personalizar esses valores para se adequarem ao layout da sua apresentação.

### Etapa 4: definir o clique do hiperlink da macro

Agora vem a parte em que você define o clique do hiperlink da macro. Você precisará fornecer um nome de macro como parâmetro.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

Neste exemplo, definimos o clique do hiperlink da macro como "TestMacro". Quando o usuário clica na AutoForma, esta macro será acionada.

### Etapa 5: recuperar informações

Você também pode recuperar informações sobre o hiperlink definido.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Essas linhas de código permitem imprimir a URL externa e o tipo de ação do hiperlink.

E é isso! Você definiu com sucesso um clique de hiperlink de macro em sua apresentação usando Aspose.Slides for .NET.

## Conclusão

Neste tutorial, aprendemos como definir um clique de hiperlink de macro em sua apresentação usando Aspose.Slides for .NET. Este pode ser um recurso valioso para criar apresentações interativas e dinâmicas que envolvam seu público. Com Aspose.Slides for .NET, você tem uma ferramenta poderosa à sua disposição para levar o desenvolvimento de sua apresentação para o próximo nível.

 Agora é hora de experimentar e criar apresentações cativantes com hiperlinks de macro personalizados. Sinta-se à vontade para explorar[Documentação do Aspose.Slides para .NET](https://reference.aspose.com/slides/net/) para informações e possibilidades mais detalhadas.

## FAQs (perguntas frequentes)

### Posso usar Aspose.Slides for .NET com outras linguagens de programação?
Aspose.Slides foi projetado principalmente para .NET, mas Aspose oferece bibliotecas semelhantes para outras linguagens de programação, como Java.

### O Aspose.Slides for .NET é uma biblioteca gratuita?
Aspose.Slides for .NET é uma biblioteca comercial com uma versão de teste gratuita disponível. Você pode baixá-lo em[aqui](https://releases.aspose.com/).

### Há alguma limitação no uso de macros em apresentações criadas com Aspose.Slides for .NET?
Aspose.Slides for .NET permite que você trabalhe com macros, mas você deve estar ciente das considerações de segurança e compatibilidade ao usar macros em apresentações.

### Posso personalizar a aparência da AutoForma usada para o hiperlink?
Sim, você pode personalizar a aparência da AutoForma ajustando suas propriedades, como tamanho, cor e fonte.

### Onde posso obter ajuda ou suporte para Aspose.Slides for .NET?
 Se você encontrar problemas ou tiver dúvidas, procure ajuda no fórum de suporte do Aspose[aqui](https://forum.aspose.com/).