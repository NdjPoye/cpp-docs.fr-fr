---
title: "Spécificateur final | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- final
- final_CPP
dev_langs:
- C++
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
caps.latest.revision: 7
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
ms.openlocfilehash: c9f0a638707466778e75a3eabfe838c84b0355d7
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="final-specifier"></a>Spécificateur final
Vous pouvez utiliser le mot clé `final` pour désigner les fonctions virtuelles qui ne peuvent pas être remplacées dans une classe dérivée. Vous pouvez également l'utiliser pour désigner les classes qui ne peuvent pas être héritées.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
function-declaration final;  
```  
  
```  
  
class class-name final base-classes  
```  
  
## <a name="remarks"></a>Remarques  
 `final` est contextuel et a une signification spéciale uniquement lorsqu'il est utilisé après une déclaration de fonction ou un nom de classe ; sinon, ce n'est pas un mot clé réservé.  
  
 Lorsque `final` est utilisé dans les déclarations de classes, `base-classes` est une partie facultative de la déclaration.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant utilise le mot clé `final` pour spécifier qu'une fonction virtuelle ne peut pas être remplacée.  
  
```cpp  
class BaseClass  
{  
    virtual void func() final;  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void func(); // compiler error: attempting to   
                         // override a final function  
};  
```  
  
 Pour plus d’informations sur la façon de spécifier que les fonctions de membre peuvent être substituées, consultez [spécificateur de substitution](../cpp/override-specifier.md).  
  
 L'exemple suivant utilise le mot clé `final` pour spécifier qu'une classe ne peut pas être héritée.  
  
```cpp  
class BaseClass final   
{  
};  
  
class DerivedClass: public BaseClass // compiler error: BaseClass is   
                                     // marked as non-inheritable  
{  
};  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)   
 [override, spécificateur](../cpp/override-specifier.md)
