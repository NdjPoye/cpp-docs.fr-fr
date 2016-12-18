---
title: "_mm_insert_si64, _mm_inserti_si64 | Microsoft Docs"
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
  - "_mm_inserti_si64"
  - "_mm_insert_si64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insertq, instruction"
  - "_mm_insert_si64 intrinsèque"
  - "_mm_inserti_si64 intrinsèque"
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mm_insert_si64, _mm_inserti_si64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `insertq` d'insérer des bits de son deuxième dans son premier opérande.  
  
## Syntaxe  
  
```  
__m128i _mm_insert_si64(  
   __m128i Source1,  
   __m128i Source2  
);  
__m128i _mm_inserti_si64(  
   __m128i Source1,  
   __m128i Source2  
   int Length,  
   int Index  
);  
```  
  
#### Paramètres  
 \[in\] `Source1`  
 Un champ 128 bits avec les données d'entrée dans ses 64 bits inférieurs dans lesquels il est inséré.  
  
 \[in\]    `Source2`  
 Un champ 128 bits avec les données à insérer dans ses bas bits.  Pour `_mm_insert_si64`, contient également un descripteur de champ dans ses bits élevés.  
  
 \[in\]    `Length`  
 Une constante entière qui spécifie la longueur du champ à insérer.  
  
 \[in\]    `Index`  
 Une constante entière qui spécifie l'index de bits le moins significatif du champ dans lequel les données sont insérées.  
  
## Valeur de retour  
 Un champ 128 bits dont les 64 bits inférieurs contiennent les bits d'origine du bas 64 d' `Source1` au champ de bits spécifié a remplacé par les bas bits d' `Source2`.  les 64 bits supérieurs de la valeur de retour sont indéfinis.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_mm_insert_si64`|SSE4a|  
|`_mm_inserti_si64`|SSE4a|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette intrinsèque génère des instructions d' `insertq` d'insérer des bits d' `Source2` dans `Source1`.  Il existe deux versions de cette intrinsèque : `_mm_inserti_si64`, est la version immédiate, et `_mm_insert_si64` est le non\-immédiat.  Chaque version extrait un champ de bits d'une longueur données de Source2 et l'insère dans Source1.  Les bits extraits sont les bits les plus significatifs de Source2.  Le champ Source1 dans lequel les bits sont insérés est défini par la longueur et l'index de son bit le moins significatif.  Les valeurs de longueur et l'index sont le modèle pris 64, donc \-1 et 127 sont interprètes comme 63.  Si la somme de l'index \(réduit\) et la longueur du champ \(réduite\) de bit est supérieure à 64, les résultats sont indéfinis.  Une valeur zéro pour la taille du champ est interprétée comme 64.  Si l'index de longueur de champ et de bits sont les deux zéro, 63:0 de bits d' `Source2` sont insérés dans `Source1`.  Si la taille du champ est zéro mais l'index de bit est différente de zéro, les résultats sont indéfinis.  
  
 Dans un appel à \_mm\_insert\_si64, la taille du champ est contenue dans le 77:72 de bits de Source2 et l'index dans le 69:64 de bits.  
  
 Si vous appelez `_mm_inserti_si64`avec les arguments que le compilateur ne peut pas déterminer pour être des constantes entières, le compilateur génère du code pour compacter ces valeurs dans un registre XMM et appeler `_mm_insert_si64`.  
  
 Pour déterminer la prise en charge du matériel pour l'instruction d' `insertq` appelez l'intrinsèque de `__cpuid` avec `InfoType=0x80000001` et le bit de contrôle 6 d' `CPUInfo[2] (ECX)`.  Ce bit est 1 si l'instruction est prise en charge, et 0 sinon.  Si vous exécutez le code qui utilise cette intrinsèque sur le matériel qui ne prend pas en charge l'instruction d' `insertq` , les résultats sont imprévisibles.  
  
## Exemple  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source1, source2, source3, result1, result2, result3;  
  
int  
main()  
{  
  
    __int64 mask;  
  
    source1.ui64[0] = 0xffffffffffffffffll;  
    source2.ui64[0] = 0xfedcba9876543210ll;  
    source2.ui64[1] = 0xc10;  
    source3.ui64[0] = source2.ui64[0];  
  
    result1.m = _mm_insert_si64 (source1.m, source2.m);  
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);  
    mask = 0xffff << 12;  
    mask = ~mask;  
    result3.ui64[0] = (source1.ui64[0] & mask) |  
                      ((source2.ui64[0] & 0xffff) << 12);  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
  
}  
```  
  
  **result1 \= 0xfffffffff3210fff**  
**result2 \= 0xfffffffff3210fff**  
**result3 \= 0xfffffffff3210fff**   
## détail de FIN Microsoft  
 copyright 2007 par Advanced Micro Devices, Inc.  Tous droits réservés.  reproduit avec l'autorisation d'Advanced Micro Devices, Inc.  
  
## Voir aussi  
 [\_mm\_extract\_si64, \_mm\_extracti\_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)