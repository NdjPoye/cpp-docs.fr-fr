---
title: "__rdtscp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__rdtscp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rdtscp, intrinsèque"
  - "__rdtscp, intrinsèque"
  - "rdtscp, instruction"
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __rdtscp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `rdtscp` , écrit `TSC_AUX[31:0`\] dans la mémoire, et retourne le compteur de groupe date\/heure d'heure 64 bits \(résultat d'`TSC)` .  
  
## Syntaxe  
  
```  
unsigned __int64 __rdtscp(  
   unsigned int * Aux  
);  
```  
  
#### Paramètres  
 \[out\] `Aux`  
 Pointeur vers un emplacement qui contiendra le contenu du registre spécifique à l'ordinateur `TSC_AUX[31:0]`.  
  
## Valeur de retour  
 un nombre de cycles 64 bits d'entier non signé.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__rdtscp`|famille 0Fh d'AMD TNP ou versions ultérieures|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette intrinsèque génère des instructions d' `rdtscp` .  Pour déterminer la prise en charge matérielle pour cette instruction, appelez l'intrinsèque de `__cpuid`avec `InfoType=0x80000001` et le bit de contrôle 27 d' `CPUInfo[3] (EDX)`.  Ce bit est 1 si l'instruction est prise en charge, et 0 sinon.  Si vous exécutez le code qui utilise cette intrinsèque sur le matériel qui ne prend pas en charge l'instruction d' `rdtscp` , les résultats sont imprévisibles.  
  
> [!CAUTION]
>  Contrairement à `rdtsc`, `rdtscp` est une instruction sérialisante ; néanmoins, le compilateur peut déplacer le code qui encadrent cette fonction intrinsèque.  
  
 L'interprétation de la valeur de centre technique dans cette génération de matériel diffère de celle dans les versions antérieures de [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  Consultez les manuels de matériel pour plus d'informations.  
  
 la signification de la valeur dans `TSC_AUX[31:0]` dépend du système d'exploitation.  
  
## Exemple  
  
```  
#include <intrin.h>   
#include <stdio.h>  
int main()   
{  
 unsigned __int64 i;  
 unsigned int ui;  
 i = __rdtscp(&ui);  
 printf_s("%I64d ticks\n", i);  
 printf_s("TSC_AUX was %x\n", ui);  
}  
```  
  
  **3363423610155519 battements**  
**TSC\_AUX était 0**   
## détail de FIN Microsoft  
 copyright 2007 par Advanced Micro Devices, Inc.  Tous droits réservés.  reproduit avec l'autorisation d'Advanced Micro Devices, Inc.  
  
## Voir aussi  
 [\_\_rdtsc](../intrinsics/rdtsc.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)