---
title: "__lzcnt16, __lzcnt, __lzcnt64 | Microsoft Docs"
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
  - "__lzcnt64"
  - "__lzcnt16"
  - "__lzcnt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__lzcnt, intrinsèque"
  - "lzcnt, instruction"
  - "lzcnt16, intrinsèque"
  - "lzcnt, intrinsèque"
  - "__lzcnt16, intrinsèque"
  - "lzcnt64, intrinsèque"
  - "__lzcnt64, intrinsèque"
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
caps.latest.revision: 14
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __lzcnt16, __lzcnt, __lzcnt64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Compte le nombre de zéros non significatifs dans un entier compris entre 16 et 32, \-, ou 64 octets.  
  
## Syntaxe  
  
```  
unsigned short __lzcnt16(  
   unsigned short value  
);  
unsigned int __lzcnt(  
   unsigned int value  
);  
unsigned __int64 __lzcnt64(  
   unsigned __int64 value  
);  
```  
  
#### Paramètres  
 \[in\] `value`  
 Les 16 \- 32, \-, ou 64 bits entiers non signés à analyser pour des zéros non significatifs.  
  
## Valeur de retour  
 le nombre de bits de zéro non significatif dans le paramètre d' `value` .  Si `value` est zéro, la valeur de retour est la taille de l'opérande d'entrée \(16, 32 ou 64\).  si le bit de poids fort d' `value` est un, la valeur de retour est zéro.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__lzcnt16`|manipulation de bits avancée|  
|`__lzcnt`|manipulation de bits avancée|  
|`__lzcnt64`|Manipulation de bits avancée en mode 64 bits.|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Chacune de ces intrinsèques génère des instructions d' `lzcnt` .  La taille de la valeur que l'instruction d'`lzcnt` retourne est la même que la taille de son argument.  En mode 32 bits il n'y a des registres à caractère général pas 64 bits, donc pas `lzcnt`64 bits.  
  
 Pour déterminer la prise en charge du matériel pour l'instruction d'`lzcnt` appelez l'intrinsèque de `__cpuid` avec `InfoType=0x80000001` et le bit de contrôle 5 d' `CPUInfo[2] (ECX)`.  Ce bit est 1 si l'instruction est prise en charge, et 0 sinon.  Si vous exécutez le code qui utilise cette intrinsèque sur le matériel qui ne prend pas en charge l'instruction d'`lzcnt` , les résultats sont imprévisibles.  
  
## Exemple  
  
```  
// Compile this test with: /EHsc  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __lzcnt16(us[i]);  
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __lzcnt(ui[i]);  
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
  **\_\_lzcnt16 \(0x0\) \= 16**  
 **\_\_lzcnt16 \(0xff\) \= 8**  
 **\_\_lzcnt16 \(0xffff\) \= 0**  
 **\_\_lzcnt \(0x0\) \= 32**  
 **\_\_lzcnt \(0xff\) \= 24**  
 **\_\_lzcnt \(0xffff\) \= 16**  
 **\_\_lzcnt \(0xffffffff\) \= 0**   
## détail de FIN Microsoft  
 copyright 2007 par Advanced Micro Devices, Inc.  Tous droits réservés.  reproduit avec l'autorisation d'Advanced Micro Devices, Inc.  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)