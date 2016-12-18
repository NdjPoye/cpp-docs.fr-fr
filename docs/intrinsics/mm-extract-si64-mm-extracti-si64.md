---
title: "_mm_extract_si64, _mm_extracti_si64 | Microsoft Docs"
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
  - "_mm_extracti_si64"
  - "_mm_extract_si64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extrq, instruction"
  - "_mm_extracti_si64, intrinsèque"
  - "_mm_extract_si64, intrinsèque"
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mm_extract_si64, _mm_extracti_si64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `extrq` de récupérer les bits spécifié des bits du bas 64 de son premier argument.  
  
## Syntaxe  
  
```  
__m128i _mm_extract_si64(  
   __m128i Source,  
   __m128i Descriptor  
);  
__m128i _mm_extracti_si64(  
   __m128i Source,  
   int Length,  
   int Index  
);  
```  
  
#### Paramètres  
 \[in\] `Source`  
 Un champ 128 bits avec les données d'entrée dans ses 64 bits inférieurs.  
  
 \[in\]    `Descriptor`  
 Un champ 128 bits qui décrit le champ de bits pour récupérer.  
  
 \[in\]    `Length`  
 Un entier qui spécifie la longueur du champ à récupérer.  
  
 \[in\]    `Index`  
 Un entier qui spécifie l'index du champ pour récupérer  
  
## Valeur de retour  
 Un champ 128 bits avec le champ extrait dans ses de modifier certains bits.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_mm_extract_si64`|SSE4a|  
|`_mm_extracti_si64`|SSE4a|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette intrinsèque génère des instructions d' `extrq` de récupérer des bits d' `Source`. Il existe deux versions de cette intrinsèque : `_mm_extracti_si64` est la version immédiate, et `_mm_extract_si64` est le non\-immédiat.  chaque version extrait d' `Source` qu'un champ de bits a défini par sa longueur et l'index de son bit le moins significatif.  Les valeurs de longueur et l'index sont le modèle pris 64, donc \-1 et 127 sont interprètes comme 63.  Si la somme de l'index \(réduit\) et la longueur du champ \(réduite\) est supérieure à 64, les résultats sont indéfinis.  Une valeur zéro pour la taille du champ est interprétée comme 64.  Si l'index de longueur de champ et de bits sont les deux zéro, 63:0 de bits d' `Source` sont récupérés.  Si la taille du champ est zéro mais l'index de bit est différente de zéro, les résultats sont indéfinis.  
  
 Dans un appel à \_mm\_extract\_si64, `Descriptor` contient l'index dans le de 13:8 bits et la taille du champ de données à récupérer dans le de 5:0 bits.  
  
 Si vous appelez `_mm_extracti_si64` avec les arguments que le compilateur ne peut pas déterminer pour être des constantes entières le compilateur génère du code pour compacter ces valeurs dans un registre XMM \(`Descriptor`\) et appeler `_mm_extract_si64`.  
  
 Pour déterminer la prise en charge du matériel pour l'instruction d' `extrq` , appelez l'intrinsèque de `__cpuid` avec `InfoType=0x80000001` et le bit de contrôle 6 d' `CPUInfo[2] (ECX)`.  Ce bit est 1 si l'instruction est prise en charge, et 0 sinon.  Si vous exécutez le code qui utilise ces informations intrinsèque qui ne prend pas en charge l'instruction d' `extrq` , les résultats sont imprévisibles.  
  
## Exemple  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source, descriptor, result1, result2, result3;  
  
int  
main()  
{  
    source.ui64[0] =     0xfedcba9876543210ll;  
    descriptor.ui64[0] = 0x0000000000000b1bll;  
  
    result1.m = _mm_extract_si64 (source.m, descriptor.m);  
    result2.m = _mm_extracti_si64(source.m, 27, 11);  
    result3.ui64[0] = (source.ui64[0] >> 11) & 0x7ffffff;  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
}  
```  
  
  **result1 \= 0x30eca86**  
**result2 \= 0x30eca86**  
**result3 \= 0x30eca86**   
## détail de FIN Microsoft  
 copyright 2007 par Advanced Micro Devices, Inc.  Tous droits réservés.  reproduit avec l'autorisation d'Advanced Micro Devices, Inc.  
  
## Voir aussi  
 [\_mm\_insert\_si64, \_mm\_inserti\_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)