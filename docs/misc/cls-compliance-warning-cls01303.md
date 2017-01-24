---
title: "Avertissement de conformit&#233; CLS CLS01303 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLS01303"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01303"
ms.assetid: a8aa0cda-a2dd-41da-bcc2-53221207ea70
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# Avertissement de conformit&#233; CLS CLS01303
Un littéral conforme CLS doit avoir une valeur spécifiée dans les métadonnées d’initialisation de champ qui soit exactement la même que le littéral \(ou du type sous\-jacent, si ce littéral est un enum\).  
  
 La valeur d'un champ statique littéral est spécifiée via l'utilisation de métadonnées d'initialisation de champ. Un littéral conforme à CLS doit avoir une valeur spécifiée dans les métadonnées d’initialisation de champ qui soit exactement la même que le littéral \(ou du type sous\-jacent, si ce littéral est un enum\).  
  
 Vérifiez que le littéral du champ a exactement le même type que le littéral \(ou le même type sous\-jacent, si le littéral est un enum\).  
  
 Pour plus d’informations sur la vérification de conformité CLS, consultez [CLS Compliant Assemblies](http://msdn.microsoft.com/fr-fr/3320b57e-ea55-4697-a17d-f509a36a3c93).  
  
 La déclaration suivante \(en langage d’assembly MSIL\) montre ce qui peut provoquer l’avertissement CLS01303 :  
  
```  
.field public static literal char Field2 = int32(0x00000002)  
```  
  
 Vous pouvez résoudre cet avertissement en vous assurant que le type de l’initialiseur est le même que celui du littéral :  
  
```  
.field public static literal char Field2 = char(0x00000002)  
```