---
title: "Tailles de type et de variable dans un assembly inline | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "length"
  - "Type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "assembleur inline, opérateurs"
  - "LENGTH (opérateur)"
  - "taille"
  - "SIZE (opérateur)"
  - "taille, obtenir dans l'assembleur inline"
  - "TYPE (opérateur)"
  - "variables, longueur"
  - "variables, taille"
  - "variables, type"
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Tailles de type et de variable dans un assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Le  **longueur**,  **taille**, et  **TYPE** opérateurs ont une signification limitée dans un assembly inline.  Ne peut pas être utilisés à tout avec la  `DUP`opérateur \(parce que vous ne pouvez définir des données avec les opérateurs ou les directives MASM\).  Mais vous pouvez les utiliser pour connaître la taille des types ou des variables de C ou C\+\+ :  
  
-   Le  **longueur** opérateur peut renvoyer le nombre d'éléments dans un tableau.  Elle renvoie la valeur 1 pour les variables de tableau non.  
  
-   Le  **taille** opérateur peut renvoyer la taille d'une variable C ou C\+\+.  Taille d'une variable est le produit de sa  **longueur de** et  **TYPE**.  
  
-   Le  **TYPE** opérateur peut renvoyer la taille d'une variable ou de type C ou C\+\+.  Si la variable est un tableau,  **TYPE** retourne la taille d'un élément unique du tableau.  
  
 Par exemple, si votre programme présente un élément de 8  `int`tableau,  
  
```  
int arr[8];  
```  
  
 les expressions suivantes C et assembly produisent la taille de  `arr`et de ses éléments.  
  
|\_\_asm|C|Taille|  
|-------------|-------|------------|  
|**LONGUEUR** arr|`sizeof`\(arr\)\/`sizeof`\(arr\[0\]\)|8|  
|**TAILLE de** arr|`sizeof`\(arr\)|32|  
|**TYPE** arr|`sizeof`\(arr\[0\]\)|4|  
  
 **FIN spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation du langage assembleur dans les blocs \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)