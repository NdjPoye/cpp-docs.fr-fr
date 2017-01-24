---
title: "_AddressOfReturnAddress | Microsoft Docs"
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
  - "_AddressOfReturnAddress_cpp"
  - "_AddressOfReturnAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_AddressOfReturnAddress, intrinsèque"
  - "AddressOfReturnAddress, intrinsèque"
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _AddressOfReturnAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Fournit l'adresse de l'emplacement de mémoire qui contient l'adresse de retour de la fonction active.  Cette adresse ne peut être utilisée pour accéder à d'autres emplacements de mémoire \(par exemple, les arguments de fonction\).  
  
## Syntaxe  
  
```  
void * _AddressOfReturnAddress();  
```  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_AddressOfReturnAddress`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Lorsque `_AddressOfReturnAddress` est utilisé dans un programme compilé avec [\/clr](../build/reference/clr-common-language-runtime-compilation.md), la fonction contenant l'appel d' `_AddressOfReturnAddress` est compilée comme fonction native.  Lorsque appelle aussi managés compilés par fonction dans la fonction contenant `_AddressOfReturnAddress`, `_AddressOfReturnAddress` peuvent ne pas se comporter que prévu.  
  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## Exemple  
  
```  
// compiler_intrinsics_AddressOfReturnAddress.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
// This function will print three values:  
//   (1) The address retrieved from _AddressOfReturnAdress  
//   (2) The return address stored at the location returned in (1)  
//   (3) The return address retrieved the _ReturnAddress* intrinsic  
// Note that (2) and (3) should be the same address.  
__declspec(noinline)  
void func() {  
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();  
   printf_s("%p\n", pvAddressOfReturnAddress);  
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));  
   printf_s("%p\n", _ReturnAddress());  
}  
  
int main() {  
   func();  
}  
```  
  
  **0012FF78**  
**00401058**  
**00401058**   
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)