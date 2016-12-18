---
title: "D&#233;pannage des exceptions&#160;: System.FormatException | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "FormatException (classe)"
ms.assetid: b2a4f55e-da87-4915-a053-59eb1595993d
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.FormatException
Une exception <xref:System.FormatException> est levée par une méthode qui analyse ou met en forme un type quand le format d'un argument ne correspond pas aux spécifications de paramètres de la méthode.  
  
## Dans cet article  
  
## Exceptions liées au format  
  
### Mise en forme  
 La *mise en forme* est le processus de conversion d'une instance d'une classe, d'une structure ou d'une valeur d'énumération en représentation sous forme de chaîne, généralement pour exposer la chaîne obtenue aux utilisateurs ou pour l'utiliser afin d'enregistrer l'état de l'objet.  
  
 Par exemple, <xref:System.Int32.ToString%28System.String%29?displayProperty=fullName> accepte un paramètre de chaîne qui identifie une *chaîne de format* standard ou personnalisée, puis retourne la représentation sous forme de chaîne du nombre. La méthode lève une exception <xref:System.FormatException>. Si la chaîne de format n'est pas valide ou si elle n'est pas prise en charge, une exception est levée.  
  
### Mise en forme composite  
 La *mise en forme composite* accepte une liste d'objets et une chaîne de format composite en entrée. Une chaîne de format composite se compose de texte fixe mélangé à des espaces réservés indexés, appelés éléments de format, qui correspondent aux objets de la liste. L'opération de mise en forme produit une chaîne résultante qui se compose du texte fixe d'origine mélangé à la représentation sous forme de chaîne des objets de la liste.  
  
 <xref:System.String.Format%2A?displayProperty=fullName> et <xref:System.Console.WriteLine%2A?displayProperty=fullName> sont des exemples de méthodes qui effectuent une mise en forme composite. Les méthodes qui utilisent une mise en forme composite lèvent une exception <xref:System.FormatException> si la chaîne de format n'est pas valide ou si l'index d'un élément de format est inférieur à zéro, ou supérieur ou égal au nombre d'arguments.  
  
### Analyse  
 L'*analyse* est le processus de conversion d'une chaîne qui représente un type de base du .NET Framework en ce type de base. Par exemple, une opération d'analyse permet de convertir une chaîne en nombre à virgule flottante ou en valeur de date et d'heure.  
  
 Par exemple, <xref:System.Int32.Parse%28System.String%29?displayProperty=fullName><xref:System.DateTime.Parse%2A> convertit la représentation sous forme de chaîne d’une date et d’une heure en son <xref:System.DateTime> équivalent à l’aide des informations de format propres à la culture indiquées dans le paramètre <xref:System.IformatProvider>. Si la chaîne n'est pas au bon format, l'exception <xref:System.FormatException> est levée.  
  
## Éviter FormatExceptions  
 L'article sur la référence de classe <xref:System.FormatException> comprend les principales causes et solutions des erreurs <xref:System.FormatException>.  
  
 Les sections MSDN Library [Mise en forme des types](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md) et [Analyse de chaînes](../Topic/Parsing%20Strings%20in%20the%20.NET%20Framework.md) contiennent des informations sur la façon d’analyser et de mettre en forme correctement les types.  
  
 **Mise en forme composite**  
  
 [Mise en forme composite](../Topic/Composite%20Formatting.md)  
  
 **Types numériques**  
  
|||  
|-|-|  
|[Chaînes de format numériques standard](../Topic/Standard%20Numeric%20Format%20Strings.md)|[Chaînes de format numériques personnalisées](../Topic/Custom%20Numeric%20Format%20Strings.md)|  
|[Analyse de chaînes numériques](../Topic/Parsing%20Numeric%20Strings%20in%20the%20.NET%20Framework.md)||  
  
 **Types de date et d'heure et types Timespan**  
  
|||  
|-|-|  
|[Chaînes de format de date et d'heure standard](../Topic/Standard%20Date%20and%20Time%20Format%20Strings.md)|[Chaînes de format de date et d'heure personnalisées](../Topic/Custom%20Date%20and%20Time%20Format%20Strings.md)|  
|[Chaînes de format TimeSpan standard.](../Topic/Standard%20TimeSpan%20Format%20Strings.md)|[Chaînes de format TimeSpan personnalisées](../Topic/Custom%20TimeSpan%20Format%20Strings.md)|  
|[Analyse des chaînes de date et d'heure](../Topic/Parsing%20Date%20and%20Time%20Strings%20in%20the%20.NET%20Framework.md)||  
  
 **Autres types**  
  
|||  
|-|-|  
|[Chaînes de format d'énumération](../Topic/Enumeration%20Format%20Strings.md)|[Analyse d'autres chaînes](../Topic/Parsing%20Other%20Strings%20in%20the%20.NET%20Framework.md)|