---
title: __sptr, __uptr | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __uptr_cpp
- __sptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- __sptr modifier
- __uptr modifier
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 684b9533c57d7c0ca90f18bc82f2cf6ddb65bc8e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="sptr-uptr"></a>__sptr, __uptr
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Utilisez le modificateur `__sptr` ou `__uptr` sur une déclaration de pointeur 32 bits pour spécifier comment le compilateur convertit un pointeur 32 bits en pointeur 64 bits. Un pointeur 32 bits est converti, par exemple, lorsqu'il est assigné à une variable pointeur 64 bits ou est déréférencé sur une plateforme 64 bits.  
  
 La documentation Microsoft pour la prise en charge des plateformes 64 bits fait parfois référence au bit le plus significatif d'un pointeur 32 bits comme bit de signe. Par défaut, le compilateur utilise l'extension de signe pour convertir un pointeur 32 bits en pointeur 64 bits. Autrement dit, les 32 bits les moins significatifs du pointeur 64 bits sont définis avec la valeur du pointeur 32 bits et les 32 bits les plus significatifs sont définis avec la valeur du bit de signe du pointeur 32 bits. Cette conversion génère des résultats corrects si le bit de signe est 0, pas si le bit de signe est 1. Par exemple, l'adresse 32 bits 0x7FFFFFFF retourne l'adresse 64 bits équivalente 0x000000007FFFFFFF, mais l'adresse 32 bits 0x80000000 est modifiée incorrectement en 0xFFFFFFFF80000000.  
  
 Le modificateur `__sptr`, ou pointeur signé, spécifie qu'une conversion de pointeur transforme les bits les plus significatifs d'un pointeur 64 bits en bit de signe du pointeur 32 bits. Le modificateur `__uptr`, ou pointeur non signé, spécifie qu'une conversion définit les bits les plus significatifs à zéro. Les déclarations suivantes illustrent la `__sptr` et `__uptr` modificateurs utilisés avec deux pointeurs non qualifiés, deux pointeurs qualifiés avec le [__ptr32](../cpp/ptr32-ptr64.md) type et un paramètre de fonction.  
  
```  
int * __sptr psp;  
int * __uptr pup;  
int * __ptr32 __sptr psp32;  
int * __ptr32 __uptr pup32;  
void MyFunction(char * __uptr __ptr32 myValue);  
```  
  
 Utilisez les modificateurs `__sptr` et `__uptr` avec les déclarations de pointeur. Utilisez les modificateurs dans la position d’un [qualificateur de type pointeur](../c-language/pointer-declarations.md), ce qui signifie que le modificateur doit suivre l’astérisque. Vous ne pouvez pas utiliser de modificateurs avec [des pointeurs vers membres](../cpp/pointers-to-members.md). Les modificateurs n'ont pas d'incidence sur les déclarations non pointeur.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant déclare des pointeurs 32 bits qui utilisent les modificateurs `__sptr` et `__uptr`, assigne chaque pointeur 32 bits à une variable pointeur 64 bits, puis affiche la valeur hexadécimale de chaque pointeur 64 bits. Il est compilé avec le compilateur 64 bits natif et exécuté sur une plateforme 64 bits.  
  
```cpp  
// sptr_uptr.cpp  
// processor: x64  
#include "stdio.h"  
  
int main()  
{  
    void *        __ptr64 p64;  
    void *        __ptr32 p32d; //default signed pointer  
    void * __sptr __ptr32 p32s; //explicit signed pointer  
    void * __uptr __ptr32 p32u; //explicit unsigned pointer  
  
// Set the 32-bit pointers to a value whose sign bit is 1.  
    p32d = reinterpret_cast<void *>(0x87654321);  
    p32s = p32d;  
    p32u = p32d;  
  
// The printf() function automatically displays leading zeroes with each 32-bit pointer. These are unrelated   
// to the __sptr and __uptr modifiers.   
    printf("Display each 32-bit pointer (as an unsigned 64-bit pointer):\n");  
    printf("p32d:       %p\n", p32d);   
    printf("p32s:       %p\n", p32s);  
    printf("p32u:       %p\n", p32u);  
  
    printf("\nDisplay the 64-bit pointer created from each 32-bit pointer:\n");  
    p64 = p32d;   
    printf("p32d: p64 = %p\n", p64);  
    p64 = p32s;  
    printf("p32s: p64 = %p\n", p64);  
    p64 = p32u;  
    printf("p32u: p64 = %p\n", p64);  
    return 0;  
}  
```  
  
```Output  
Display each 32-bit pointer (as an unsigned 64-bit pointer):  
p32d:       0000000087654321  
p32s:       0000000087654321  
p32u:       0000000087654321  
  
Display the 64-bit pointer created from each 32-bit pointer:  
p32d: p64 = FFFFFFFF87654321  
p32s: p64 = FFFFFFFF87654321  
p32u: p64 = 0000000087654321  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Modificateurs propres à Microsoft](../cpp/microsoft-specific-modifiers.md)
