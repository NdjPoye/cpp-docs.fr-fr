---
title: __if_exists, instruction | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __if_exists_cpp
dev_langs: C++
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c7950e2fcd933bd4748c06adf93f5ce1c271b162
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ifexists-statement"></a>__if_exists, instruction
L'instruction `__if_exists` vérifie si l'identificateur spécifié existe. Si l'identificateur existe, le bloc d'instructions spécifié est exécuté.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`identifier`|Identificateur dont vous voulez tester l'existence.|  
|`statements`|Une ou plusieurs instructions à exécuter si `identifier` existe.|  
  
## <a name="remarks"></a>Notes  
  
> [!CAUTION]
>  Pour obtenir les résultats les plus fiables, utilisez l'instruction `__if_exists` sous les contraintes suivantes.  
  
-   Appliquez l'instruction `__if_exists` uniquement aux types simples, et non aux modèles.  
  
-   Appliquez l'instruction `__if_exists` aux identificateurs à l'intérieur ou à l'extérieur d'une classe. N'appliquez pas l'instruction `__if_exists` aux variables locales.  
  
-   Utilisez l'instruction `__if_exists` uniquement dans le corps d'une fonction. En dehors du corps d'une fonction, l'instruction `__if_exists` peut tester uniquement les types entièrement définis.  
  
-   Lorsque vous vérifiez la présence de fonctions surchargées, vous ne pouvez pas effectuer le test sur une forme spécifique de la surcharge.  
  
 Le complément à la `__if_exists` instruction est la [__if_not_exists](../cpp/if-not-exists-statement.md) instruction.  
  
## <a name="example"></a>Exemple  
 Notez que cet exemple utilise des modèles, ce qui n'est pas recommandé.  
  
```  
// the__if_exists_statement.cpp  
// compile with: /EHsc  
#include <iostream>  
  
template<typename T>  
class X : public T {  
public:  
   void Dump() {  
      std::cout << "In X<T>::Dump()" << std::endl;  
  
      __if_exists(T::Dump) {  
         T::Dump();  
      }  
  
      __if_not_exists(T::Dump) {  
         std::cout << "T::Dump does not exist" << std::endl;  
      }  
   }     
};  
  
class A {  
public:  
   void Dump() {  
      std::cout << "In A::Dump()" << std::endl;  
   }  
};  
  
class B {};  
  
bool g_bFlag = true;  
  
class C {  
public:  
   void f(int);  
   void f(double);  
};  
  
int main() {   
   X<A> x1;  
   X<B> x2;  
  
   x1.Dump();  
   x2.Dump();  
  
   __if_exists(::g_bFlag) {  
      std::cout << "g_bFlag = " << g_bFlag << std::endl;  
   }  
  
   __if_exists(C::f) {  
      std::cout << "C::f exists" << std::endl;  
   }  
  
   return 0;  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions de sélection](../cpp/selection-statements-cpp.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 [__if_not_exists, instruction](../cpp/if-not-exists-statement.md)