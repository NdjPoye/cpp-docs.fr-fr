---
title: "__ll_lshift | Microsoft Docs"
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
  - "__ll_lshift_cpp"
  - "__ll_lshift"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ll_lshift, intrinsèque"
  - "__ll_lshift, intrinsèque"
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __ll_lshift
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Déplace le valeur 64 bits fourni vers la gauche selon le nombre de bits spécifié.  
  
## Syntaxe  
  
```  
unsigned __int64 __ll_lshift(  
   unsigned __int64 Mask,  
   int nBit  
);  
```  
  
#### Paramètres  
 \[in\] `Mask`  
 La valeur entière 64 bits pour accéder à gauche.  
  
 \[in\] `nBit`  
 le nombre de bits à déplacer.  
  
## Valeur de retour  
 Le masque est déplacé à gauche par les bits d' `nBit` .  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__ll_lshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Si vous compilez votre programme à l'aide de l'architecture de 64 bits et `nBit` est supérieur à 63, le nombre de bits à déplacer est le modulo 64 d' `nBit` .  Si vous compilez votre programme à l'aide de l'architecture de 32 bits et `nBit` est supérieur à 31, le nombre de bits à déplacer est le modulo 32 d' `nBit` .  
  
 `ll` dans le nom indique qu'il s'agit d'une opération sur `long long` \(`__int64`\).  
  
## Exemple  
  
```  
// ll_lshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_lshift)  
  
int main()  
{  
   unsigned __int64 Mask = 0x100;  
   int nBit = 8;  
   Mask = __ll_lshift(Mask, nBit);  
   cout << hex << Mask << endl;  
}  
```  
  
## Sortie  
  
```  
10000  
```  
  
 **Remarque** il n'y a aucune version non signée de l'opération de décalage vers la gauche.  En effet `__ll_lshift` utilise déjà un paramètre d'entrée non signé.  Contrairement au décalage vers la droite, il n'y a aucune dépendance de signe pour le décalage vers la gauche, parce que le bit le moins significatif dans le résultat est toujours la valeur zéro quel que soit le signe de la valeur déplacée.  
  
### TERMINEZ le détail de Microsoft  
  
## Voir aussi  
 [\_\_ll\_rshift](../intrinsics/ll-rshift.md)   
 [\_\_ull\_rshift](../intrinsics/ull-rshift.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)