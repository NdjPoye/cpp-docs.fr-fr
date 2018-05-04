---
title: __ptr32, __ptr64 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53fafb1e7be45cd4b48ce51e787b6338dd0f7324
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 `__ptr32` représente un pointeur natif sur un système 32 bits, tandis que `__ptr64` représente un pointeur natif sur un système 64 bits.  
  
 L'exemple suivant montre comment déclarer chacun de ces types pointeur :  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 Sur un système 32 bits, un pointeur déclaré avec `__ptr64` est tronqué à un pointeur 32 bits. Sur un système 64 bits, un pointeur déclaré avec `__ptr32` est converti en pointeur 64 bits.  
  
> [!NOTE]
>  Vous ne pouvez pas utiliser `__ptr32` ou `__ptr64` lors de la compilation avec **/CLR : pure**. Sinon, l'erreur `Compiler Error C2472` est générée. Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment déclarer et allouer des pointeurs avec les mots clés `__ptr32` et `__ptr64`.  
  
```  
#include <cstdlib>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    int * __ptr32 p32;  
    int * __ptr64 p64;  
  
    p32 = (int * __ptr32)malloc(4);  
    *p32 = 32;  
    cout << *p32 << endl;  
  
    p64 = (int * __ptr64)malloc(4);  
    *p64 = 64;  
    cout << *p64 << endl;  
}  
```  
  
```Output  
32  
64  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Types fondamentaux](../cpp/fundamental-types-cpp.md)