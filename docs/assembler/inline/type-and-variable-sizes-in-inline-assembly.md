---
title: Type de tailles et de Variable dans un Assembly Inline | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- length
- Type
dev_langs: C++
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee9edf9430c0333317a767e8f8c114453a6d80f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>Tailles de type et de variable dans l'assembly inline
**Section spécifique à Microsoft**  
  
 Le **longueur**, **taille**, et **TYPE** opérateurs ont une signification limitée dans l’assembleur inline. Ils ne peuvent pas du tout être utilisés avec l'opérateur `DUP` (car vous ne pouvez pas définir des données avec des directives ou des opérateurs MASM). Toutefois, vous pouvez les utiliser pour rechercher la taille des variables ou types C ou C++ :  
  
-   Le **longueur** opérateur peut retourner le nombre d’éléments dans un tableau. Il retourne la valeur 1 pour les variables non-tableau.  
  
-   Le **taille** opérateur peut retourner la taille d’une variable C ou C++. Taille d’une variable est le produit de ses **longueur** et **TYPE**.  
  
-   Le **TYPE** opérateur peut retourner la taille d’une variable ou de type C ou C++. Si la variable est un tableau, **TYPE** retourne la taille d’un seul élément du tableau.  
  
 Par exemple, si votre programme comporte un tableau `int` de 8 éléments,  
  
```  
int arr[8];  
```  
  
 les expressions C et d'assembly suivantes génèrent la taille d'un tableau `arr` et de ses éléments.  
  
|__asm|C|Size|  
|-------------|-------|----------|  
|**LONGUEUR** arr|`sizeof`(arr)/`sizeof`(arr[0])|8|  
|**TAILLE** arr|`sizeof`(arr)|32|  
|**TYPE** arr|`sizeof`(arr[0])|4|  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation du langage assembleur dans les blocs __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)