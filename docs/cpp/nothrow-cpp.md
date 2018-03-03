---
title: nothrow (C++) | Documents Microsoft
ms.custom: 
ms.date: 01/03/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- nothrow_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5e0f5f40fbcfcb95952fd956060801e862e9cdaf
ms.sourcegitcommit: c2e990450ccd528d85b2783fbc63042612987cfd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2018
---
# <a name="nothrow-c"></a>nothrow (C++)

**Section spécifique à Microsoft**

Attribut étendu de `__declspec` qui peut être utilisé dans la déclaration de fonctions.

## <a name="syntax"></a>Syntaxe  
  
> *type de retour* __declspec (nothrow) [*convention d’appel*] *-nom de la fonction* ([*-liste d’arguments*])

## <a name="remarks"></a>Notes

Nous recommandons que tous les nouveaux codes à utiliser le [noexcept](noexcept-cpp.md) opérateur plutôt que `__declspec(nothrow)`.

Cet attribut indique au compilateur que la fonction déclarée et les fonctions qu'elle appelle ne lèvent jamais d'exception. Toutefois, il n’applique pas la directive. En d’autres termes, elle ne génère jamais [std::terminate](../standard-library/exception-functions.md#terminate) à appeler, contrairement aux `noexcept`, ou dans **std:c ++ 17** (Visual Studio 2017 15,5 et versions ultérieures), le mode `throw()`.

Avec le modèle synchrone de gestion des exceptions, utilisé désormais par défaut, le compilateur peut éliminer les mécanismes de suivi de la durée de vie de certains objets non déroulables dans une telle fonction, et peut réduire considérablement la taille du code. Étant donné la directive de préprocesseur suivante, les trois déclarations de fonction ci-dessous sont équivalentes dans **/std : c ++ 14** mode :

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

Dans **/std : c ++ 17** mode, `throw()` n’équivaut pas à ceux qui utilisent `__declspec(nothrow)` car elle force `std::terminate` d’être appelée si une exception est levée à partir de la fonction.

Le `void __stdcall f3() throw();` déclaration utilise la syntaxe définie par la norme C++. Dans C ++ 17 le `throw()` mot clé a été déconseillé.

**FIN de la section spécifique à Microsoft**

## <a name="see-also"></a>Voir aussi

[__declspec](../cpp/declspec.md)  
[noexcept](noexcept-cpp.md)  
[Mots clés](../cpp/keywords-cpp.md)  
