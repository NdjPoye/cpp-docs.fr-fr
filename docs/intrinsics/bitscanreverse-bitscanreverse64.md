---
title: "_BitScanReverse, _BitScanReverse64 | Microsoft Docs"
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
  - "_BitScanReverse64"
  - "_BitScanReverse_cpp"
  - "_BitScanReverse"
  - "_BitScanReverse64_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_BitScanReverse intrinsic"
  - "BitScanReverse intrinsic"
  - "bsr instruction"
ms.assetid: 2520a207-af8b-4aad-9ae7-831abeadf376
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _BitScanReverse, _BitScanReverse64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Rechercher les données de masque du bit le plus significatif \(MSB\) au bit le moins significatif \(LSB\) pour un bit défini \(1\).  
  
## Syntaxe  
  
```  
unsigned char _BitScanReverse(    unsigned long * Index,    unsigned long Mask ); unsigned char _BitScanReverse64(    unsigned long * Index,    unsigned __int64 Mask );  
```  
  
#### Paramètres  
 \[out\] `Index`  
 Chargé avec la position de bit du premier bit défini \(1\) détecté.  
  
 \[in\] `Mask`  
 Valeur 32 bits ou 64 bits à rechercher.  
  
## Valeur de retour  
 Différent de zéro si `Index` a été défini ou 0 si aucun bit défini n'a été détecté.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|Header|  
|-----------------|------------------|------------|  
|`_BitScanReverse`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_BitScanReverse64`|ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]||  
  
## Exemple  
  
```  
// BitScanReverse.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_BitScanReverse)  
  
int main()  
{  
   unsigned long mask = 0x1000;  
   unsigned long index;  
   unsigned char isNonzero;  
  
   cout << "Enter a positive integer as the mask: " << flush;  
   cin >> mask;  
   isNonzero = _BitScanReverse(&index, mask);  
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
Mask: 12 Index: 3  
```  
  
### FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)