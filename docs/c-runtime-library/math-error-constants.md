---
title: "Constantes d&#39;erreur math&#233;matique | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_PLOSS"
  - "_UNDERFLOW"
  - "_TLOSS"
  - "_SING"
  - "_DOMAIN"
  - "_OVERFLOW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_DOMAIN (constante)"
  - "_OVERFLOW (constante)"
  - "_PLOSS (constante)"
  - "_SING (constante)"
  - "_TLOSS (constante)"
  - "_UNDERFLOW (constante)"
  - "DOMAIN (constante)"
  - "constantes d'erreur mathématique"
  - "OVERFLOW (constante)"
  - "PLOSS (constante)"
  - "SING (constante)"
  - "TLOSS (constante)"
  - "UNDERFLOW (constante)"
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Constantes d&#39;erreur math&#233;matique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <math.h>  
  
```  
  
## Notes  
 Les routines mathématiques de la bibliothèque d'exécutables peuvent générer des constantes d'erreurs mathématique.  
  
 Ces erreurs, décrites comme suit, correspondent aux types d'exception définis dans MATH.H et sont retournées par la fonction `_matherr` lorsqu'une erreur mathématique se produit.  
  
|Constante|Signification|  
|---------------|-------------------|  
|`_DOMAIN`|L'argument à utliser est dans le domaine extérieur de la fonction.|  
|`_OVERFLOW`|Le résultat est trop grand pour être représenté dans le type de retour de la fonction.|  
|`_PLOSS`|Perte partielle de certitude du résultat rencontrée.|  
|`_SING`|Singularité d'arguments : l'argument à utiliser a une valeur non conforme. \(Par exemple, la valeur 0 est transmise à une fonction qui nécessite une valeur différente de zéro.\)|  
|`_TLOSS`|Perte complète de précision est survenue.|  
|`_UNDERFLOW`|Le résultat est trop petit pour être représenté.|  
  
## Voir aussi  
 [\_matherr](../c-runtime-library/reference/matherr.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)