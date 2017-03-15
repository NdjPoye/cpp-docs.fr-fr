---
title: "Sp&#233;cificateurs | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "spécificateurs de déclaration"
  - "déclarations, spécificateurs"
  - "spécificateurs, dans les déclarations"
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cificateurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit le composant *decl\-specifiers* \(spécificateurs de déclaration\) d'une [déclaration](../misc/declarations.md).  
  
 Les espaces réservés et les mots clés de langage suivants sont des spécificateurs de déclaration :  
  
 *storage\-class\-specifier*  
  
 *type\-specifier*  
  
 *function\-specifier*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [typedef](http://msdn.microsoft.com/fr-fr/cc96cf26-ba93-4179-951e-695d1f5fdcf1)  
  
 [\_\_declspec](../cpp/declspec.md) `(` *extended\-decl\-modifier\-seq* `)`  
  
## Notes  
 La partie *decl\-specifiers* d'une déclaration est la plus longue séquence de *decl\-specifiers* pouvant être prise pour indiquer un nom de type, sans inclure le pointeur ni les modificateurs de référence.  Le reste de la déclaration est l'élément *declarator* qui inclut le nom introduit.  
  
 Le tableau suivant répertorie quatre déclarations, puis présente les composants *decl\-specifers* et *declarator* de chacune d'elles séparément.  
  
|Déclaration|*decl\-specifiers*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|`char`|`*lpszAppName`|  
|`typedef char * LPSTR;`|`char`|`*LPSTR`|  
|`const int func1();`|`const int`|`func1`|  
|`volatile void *pvvObj;`|`volatile void`|`*pvvObj`|  
  
 Comme `signed`, `unsigned`, `long` et `short` impliquent tous `int`, un nom `typedef` suivant l'un de ces mots clés est pris pour être membre de *declarator\-list*, et non de *decl\-specifiers*.  
  
> [!NOTE]
>  Comme un nom peut être redéclaré, sa traduction est soumise à la déclaration la plus récente de la portée actuelle.  Une nouvelle déclaration peut affecter la façon dont les noms sont interprétés par le compilateur, notamment des noms `typedef`.  
  
## Voir aussi  
 [Déclarations](../misc/declarations.md)