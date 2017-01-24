---
title: "__rdtsc | Microsoft Docs"
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
  - "__rdtsc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__rdtsc, intrinsèque"
  - "rdtsc, instruction"
  - "Lecture du compteur d’horodatage, instruction"
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __rdtsc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `rdtsc` , qui retourne le groupe date\/heure de temps processeur.  Le groupe date\/heure du temps processeur stocke le nombre de cycles d'horloge depuis la dernière réinitialisation.  
  
## Syntaxe  
  
```  
unsigned __int64 __rdtsc();  
```  
  
## Valeur de retour  
 Entier non signé 64 bits qui représente un nombre de cycles.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__rdtsc`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette routine est disponible uniquement comme intrinsèque.  
  
 L'interprétation de la valeur de centre technique dans cette génération de matériel diffère de celle dans les versions antérieures de [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  Consultez les manuels de matériel pour plus d'informations.  
  
## Exemple  
  
```  
// rdtsc.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__rdtsc)  
  
int main()  
{  
    unsigned __int64 i;  
    i = __rdtsc();  
    printf_s("%I64d ticks\n", i);  
}  
```  
  
  **3363423610155519 battements**   
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)