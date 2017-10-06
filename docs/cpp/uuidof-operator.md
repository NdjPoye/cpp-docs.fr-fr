---
title: "opérateur __uuidof | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
dev_langs:
- C++
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 172ed545eb2c46db8df12e3e12a2296a5f172a1f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="uuidof-operator"></a>__uuidof, opérateur
**Section spécifique à Microsoft**  
  
 Récupère le GUID associé à l’expression.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      __uuidof (  
   expression   
)  
```  
  
## <a name="remarks"></a>Remarques  
 Le *expression* peut être un nom de type, un pointeur, une référence ou un tableau de ce type, un modèle spécialisé sur ces types, ou une variable de ces types. L’argument est valide tant que le compilateur peut l’utiliser pour rechercher le GUID attaché.  
  
 Un cas spécial de cette intrinsèque est lorsque soit **0** ou **NULL** est fournie comme argument. Dans ce cas, `__uuidof` retourne un GUID composé de zéros.  
  
 Utilisez ce mot clé pour extraire le GUID associé à :  
  
-   Un objet par le [uuid](../cpp/uuid-cpp.md) attributs étendus.  
  
-   Un bloc de bibliothèque est créé avec le [module](../windows/module-cpp.md) attribut.  
  
> [!NOTE]
>  Dans une version debug, `__uuidof` toujours Initialise un objet dynamiquement (lors de l’exécution). Dans une version Release, `__uuidof` peut initialiser statiquement (au moment de la compilation) un objet.  
  
## <a name="example"></a>Exemple  
 Le code suivant (compilé avec ole32.lib) affiche l’uuid d’un bloc de bibliothèque créé avec l’attribut de module :  
  
```  
// expre_uuidof.cpp  
// compile with: ole32.lib  
#include "stdio.h"  
#include "windows.h"  
  
[emitidl];  
[module(name="MyLib")];  
[export]  
struct stuff {  
   int i;  
};  
  
int main() {  
   LPOLESTR lpolestr;  
   StringFromCLSID(__uuidof(MyLib), &lpolestr);  
   wprintf_s(L"%s", lpolestr);  
   CoTaskMemFree(lpolestr);  
}  
```  
  
## <a name="comments"></a>Commentaires  
 Dans les cas où le nom de la bibliothèque n’est plus dans la portée, vous pouvez utiliser __LIBID\_ au lieu de `__uuidof`. Exemple :  
  
```  
StringFromCLSID(__LIBID_, &lpolestr);  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Mots clés](../cpp/keywords-cpp.md)
