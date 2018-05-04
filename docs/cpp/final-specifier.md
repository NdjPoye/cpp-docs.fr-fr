---
title: Spécificateur final | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- final_CPP
dev_langs:
- C++
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82fb9e13fc5dbbafcc37905716a37322b2966c6d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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
  
## <a name="remarks"></a>Notes  
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