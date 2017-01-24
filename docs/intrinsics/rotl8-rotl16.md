---
title: "_rotl8, _rotl16 | Microsoft Docs"
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
  - "_rotl8"
  - "_rotl16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_rotl16 intrinsic"
  - "_rotl8 intrinsic"
ms.assetid: 8c519ab6-aef9-4f07-a387-daee8408368f
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _rotl8, _rotl16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Faire pivoter les valeurs d'entrée vers la gauche pour le bit le plus significatif \(MSB\) d'un nombre spécifié de positions de bits.  
  
## Syntaxe  
  
```  
unsigned char _rotl8(     unsigned char value,     unsigned char shift  ); unsigned short _rotl16(     unsigned short value,     unsigned char shift  );  
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
|`_rotl8`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_rotl16`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Contrairement à une opération de décalage vers la gauche, lors de l'exécution d'une rotation vers la gauche, les bits de poids fort qui se trouvent hors limite sont placés dans les positions de bits les moins significatives.  
  
## Exemple  
  
```  
// rotl.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotl8, _rotl16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x left by %d bits gives 0x%x\n", c,  
               i, _rotl8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x left by %d bits gives 0x%x\n",  
            s, nBit, _rotl16(s, nBit));  
}  
```  
  
  **La rotation de 0x41 vers la gauche de 0 bit donne 0x41**  
**La rotation de 0x41 vers la gauche de 1 bit donne 0x82**  
**La rotation de 0x41 vers la gauche de 2 bits donne 0x5**  
**La rotation de 0x41 vers la gauche de 3 bits donne 0xa**  
**La rotation de 0x41 vers la gauche de 4 bits donne 0x14**  
**La rotation de 0x41 vers la gauche de 5 bits donne 0x28**  
**La rotation de 0x41 vers la gauche de 6 bits donne 0x50**  
**La rotation de 0x41 vers la gauche de 7 bits donne 0xa0**  
**La rotation de la valeur courte non signée 0x12 vers la gauche de 10 bits donne 0x4800**   
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [\_rotr8, \_rotr16](../intrinsics/rotr8-rotr16.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)