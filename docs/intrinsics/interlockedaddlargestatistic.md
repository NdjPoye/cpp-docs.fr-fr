---
title: "_InterlockedAddLargeStatistic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedAddLargeStatistic"
  - "_InterlockedAddLargeStatistic_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedAddLargeStatistic, intrinsèque"
  - "InterlockedAddLargeStatistic, intrinsèque"
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _InterlockedAddLargeStatistic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Exécute une addition verrouillées dans lequel le premier opérande est une valeur 64 bits.  
  
## Syntaxe  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### Paramètres  
 \[in, out\]  `Addend`  
 Un pointeur vers le premier opérande à l'addition.  La valeur désignée est remplacée par le résultat de l'addition.  
  
 \[in\] `Value`  
 Le deuxième ; valeur à ajouter au premier opérande.  
  
## Valeur de retour  
 La valeur du deuxième.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette intrinsèque n'est pas atomique car elle est implémentée comme deux instructions verrouillées distinctes.  Une lecture 64 bits atomique qui se produit sur un autre thread pendant l'exécution de cette intrinsèque peut provoquer une valeur non cohérente est lue.  
  
 Cette fonction se comporte comme un cloisonnement en lecture\-écriture.  Pour plus d'informations, consultez [\_ReadWriteBarrier](../intrinsics/readwritebarrier.md).  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)