---
title: "__emul, __emulu | Microsoft Docs"
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
  - "__emulu_cpp"
  - "__emul"
  - "__emul_cpp"
  - "__emulu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__emul, intrinsèque"
  - "__emulu, intrinsèque"
ms.assetid: 79545236-cca2-40b8-a4e1-8abce9b26311
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __emul, __emulu
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Effectue des multiplications dépassant du ce qu'un entier 32 bits peut contenir.  
  
## Syntaxe  
  
```  
__int64 __emul(  
   int a,  
   int b  
);  
unsigned __int64 __emulu(  
   unsigned int a,  
   unsigned int b  
);  
```  
  
#### Paramètres  
 \[in\] `a`  
 le premier opérande entier de la multiplication.  
  
 \[in\] `b`  
 le deuxième opérande entier de la multiplication.  
  
## Valeur de retour  
 le résultat de la multiplication.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__emul`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__emulu`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 `__emul` prend deux valeurs signés 32 bits et retourne le résultat de la multiplication comme valeur d'entier signé 64 bits.  
  
 `__emulu` prend deux valeurs d'entiers 32 bits non signé et retourne le résultat de la multiplication comme valeur entière non signé 64 bits.  
  
## Exemple  
  
```  
// emul.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__emul)  
#pragma intrinsic(__emulu)  
  
int main()  
{  
   int a = -268435456;   
   int b = 2;   
  
   __int64 result = __emul(a, b);  
  
   cout << a << " * " << b << " = " << result << endl;  
  
   unsigned int ua = 0xFFFFFFFF; // Dec value: 4294967295  
   unsigned int ub = 0xF000000;  // Dec value: 251658240  
  
   unsigned __int64 uresult = __emulu(ua, ub);  
  
   cout << ua << " * " << ub << " = " << uresult << endl;  
  
}  
```  
  
## Sortie  
  
```  
-268435456 * 2 = -536870912  
4294967295 * 251658240 = 1080863910317260800  
```  
  
### TERMINEZ le détail de Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)