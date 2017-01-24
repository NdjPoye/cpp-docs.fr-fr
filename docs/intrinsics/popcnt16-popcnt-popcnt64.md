---
title: "__popcnt16, __popcnt, __popcnt64 | Microsoft Docs"
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
  - "__popcnt64"
  - "__popcnt"
  - "__popcnt16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "popcnt, instruction"
  - "__popcnt16"
  - "__popcnt64"
  - "__popcnt"
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __popcnt16, __popcnt, __popcnt64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Compte le nombre de bits un \(dénombrement de la population\) dans un entier non signé 16 \- 32, \-, ou 64 octets.  
  
## Syntaxe  
  
```  
unsigned short __popcnt16(  
   unsigned short value  
);  
unsigned int __popcnt(  
   unsigned int value  
);  
unsigned __int64 __popcnt64(  
   unsigned __int64 value  
);  
```  
  
#### Paramètres  
 \[in\] `value`  
 Le \(16, 32\), ou entier non signé 64 bits pour lequel vous souhaitez le dénombrement de la population.  
  
## Valeur de retour  
 le nombre de bits un dans le paramètre d' `value` .  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__popcnt16`|manipulation de bits avancée|  
|`__popcnt`|manipulation de bits avancée|  
|`__popcnt64`|Manipulation de bits avancée en mode 64 bits.|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Chacune de ces intrinsèques génère des instructions d'`popcnt` .  La taille de la valeur que l'instruction d'`popcnt` retourne est la même que la taille de son argument.  En mode 32 bits il n'y a des registres à caractère général pas 64 bits, donc pas `popcnt`64 bits.  
  
 Pour déterminer la prise en charge du matériel pour l'instruction d' `popcnt`, appelez l'intrinsèque de `__cpuid` avec `InfoType=0x00000001` et le bit de contrôle 23 d' `CPUInfo[2] (ECX)`.  Ce bit est 1 si l'instruction est prise en charge, et 0 sinon.  Si vous exécutez le code qui utilise cette intrinsèque sur le matériel qui ne prend pas en charge l'instruction d' `popcnt` , les résultats sont imprévisibles.  
  
## Exemple  
  
```  
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
    usr = __popcnt16(us[i]);  
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __popcnt(ui[i]);  
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
  **\_\_popcnt16 \(0x0\) \= 0**  
 **\_\_popcnt16 \(0xff\) \= 8**  
 **\_\_popcnt16 \(0xffff\) \= 16**  
 **\_\_popcnt \(0x0\) \= 0**  
 **\_\_popcnt \(0xff\) \= 8**  
 **\_\_oopcnt \(0xffff\) \= 16**  
 **\_\_popcnt \(0xffffffff\) \= 32**   
## détail de FIN Microsoft  
 copyright 2007 par Advanced Micro Devices, Inc.  Tous droits réservés.  reproduit avec l'autorisation d'Advanced Micro Devices, Inc.  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)