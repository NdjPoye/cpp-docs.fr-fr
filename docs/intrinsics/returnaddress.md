---
title: "_ReturnAddress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReturnAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReturnAddress, intrinsèque"
  - "ReturnAddress, intrinsèque"
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _ReturnAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Spécifique à Microsoft  
 L'intrinsèque de `_ReturnAddress` fournit l'adresse de l'instruction dans l'appel de la fonction qui sera exécuté après le contrôle retourne à l'appelant.  
  
 Générez le programme et l'étape suivants parcourir dans le débogueur.  Comme vous parcourez le programme, notez l'adresse retournée à partir de `_ReturnAddress`.  Ensuite, immédiatement après le retour de la fonction où `_ReturnAddress` a été utilisé, ouvrez [Comment : utiliser la fenêtre Code Machine](../Topic/How%20to:%20Use%20the%20Disassembly%20Window.md) et notez que l'adresse de l'instruction suivante d'être les correspondances exécutées que l'adresse que a été retourné d' `_ReturnAddress`.  
  
 Les optimisations telles que la fonctionnalité inline peuvent affecter l'adresse de retour.  par exemple, si l'exemple de programme ci\-dessous est compilé avec [\/Ob1](../build/reference/ob-inline-function-expansion.md), `inline_func` sera inline dans l'appel de la fonction, `main`.  Par conséquent, les appels à `_ReturnAddress` d' `inline_func` et à `main` remontera chaque produit la même valeur.  
  
 Lorsque `_ReturnAddress` est utilisé dans un programme compilé avec [\/clr](../build/reference/clr-common-language-runtime-compilation.md), la fonction contenant l'appel d' `_ReturnAddress` sera compilée comme fonction native.  Lorsque appelle aussi managés compilés par fonction dans la fonction contenant `_ReturnAddress`, `_ReturnAddress` peuvent ne pas se comporter que prévu.  
  
## Configuration requise  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Exemple  
  
```  
// compiler_intrinsics__ReturnAddress.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_ReturnAddress)  
  
__declspec(noinline)  
void noinline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
__forceinline  
void inline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
int main(void)  
{  
   noinline_func();   
   inline_func();  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
  
   return 0;  
}  
```  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [\_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)