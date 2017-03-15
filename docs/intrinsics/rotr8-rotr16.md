---
title: "_rotr8, _rotr16 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_rotr16"
  - "_rotr8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_rotr16 intrinsic"
  - "_rotr8 intrinsic"
ms.assetid: dfbd2c82-82b4-427a-ad52-51609027ebff
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _rotr8, _rotr16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Faire pivoter les valeurs d'entrée vers la droite pour le bit le moins significatif \(LSB\) d'un nombre spécifié de positions de bits.  
  
## Syntaxe  
  
```  
unsigned char _rotr8(     unsigned char value,     unsigned char shift  ); unsigned short _rotr16(     unsigned short value,     unsigned char shift  );  
```  
  
#### Paramètres  
 \[in\] `value`  
 Valeur qui doit faire l'objet d'une rotation.  
  
 \[in\] `shift`  
 Nombre de bits de rotation.  
  
## Valeur de retour  
 Valeur ayant fait l'objet d'une rotation.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_rotr8`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_rotr16`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Contrairement à une opération de décalage vers la droite, lors de l'exécution d'une rotation vers la droite, les bits de poids faible qui se trouvent hors limite sont placés dans les positions de bits de poids fort.  
  
## Exemple  
  
```  
// rotr.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotr8, _rotr16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x right by %d bits gives 0x%x\n", c,  
                i, _rotr8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x right by %d bits "  
             "gives 0x%x\n",  
            s, nBit, _rotr16(s, nBit));  
}  
```  
  
  **La rotation de 0x41 vers la droite de 0 bit donne 0x41**  
**La rotation de 0x41 vers la droite de 1 bit donne 0xa0**  
**La rotation de 0x41 vers la droite de 2 bits donne 0x50**  
**La rotation de 0x41 vers la droite de 3 bits donne 0x28**  
**La rotation de 0x41 vers la droite de 4 bits donne 0x14**  
**La rotation de 0x41 vers la droite de 5 bits donne 0xa**  
**La rotation de 0x41 vers la droite de 6 bits donne 0x5**  
**La rotation de 0x41 vers la droite de 7 bits donne 0x82**  
**La rotation de la valeur courte non signée 0x12 vers la droite de 10 bits donne 0x480**   
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [\_rotl8, \_rotl16](../intrinsics/rotl8-rotl16.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)