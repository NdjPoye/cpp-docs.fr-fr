---
title: "_BitScanForward, _BitScanForward64 | Microsoft Docs"
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
  - "_BitScanForward"
  - "_BitScanForward_cpp"
  - "_BitScanForward64_cpp"
  - "_BitScanForward64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_BitScanForward intrinsic"
  - "BitScanForward intrinsic"
  - "bsf instruction"
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _BitScanForward, _BitScanForward64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Rechercher les données de masque du bit le moins significatif \(LSB\) au bit le plus significatif \(MSB\) pour un bit défini \(1\).  
  
## Syntaxe  
  
```  
unsigned char _BitScanForward(    unsigned long * Index,    unsigned long Mask ); unsigned char _BitScanForward64(    unsigned long * Index,    unsigned __int64 Mask );  
```  
  
#### Paramètres  
 \[out\] `Index`  
 Chargé avec la position de bit du premier bit défini \(1\) détecté.  
  
 \[in\] `Mask`  
 Valeur 32 bits ou 64 bits à rechercher.  
  
## Valeur de retour  
 0 si le masque est zéro ; différent de zéro dans le cas contraire.  
  
## Notes  
 Si un bit défini est détecté, la position de bit du premier bit défini détecté est retournée dans le premier paramètre.  Si aucun bit défini n'est détecté, 0 est retourné ; dans le cas contraire, 1 est retourné.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_BitScanForward`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_BitScanForward64`|ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Exemple  
  
```  
// BitScanForward.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_BitScanForward)  
  
int main()  
{  
   unsigned long mask = 0x1000;  
   unsigned long index;  
   unsigned char isNonzero;  
  
   cout << "Enter a positive integer as the mask: " << flush;  
   cin >> mask;  
   isNonzero = _BitScanForward(&index, mask);  
   if (isNonzero)  
   {  
      cout << "Mask: " << mask << " Index: " << index << endl;  
   }  
   else  
   {  
      cout << "No set bits found.  Mask is zero." << endl;  
   }  
}  
```  
  
## Entrée  
  
```  
12  
```  
  
## Résultat de l'exemple  
  
```  
Enter a positive integer as the mask:   
Mask: 12 Index: 2  
```  
  
### FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)