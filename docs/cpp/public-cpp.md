---
title: public (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- public_cpp
dev_langs:
- C++
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
caps.latest.revision: 10
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
ms.openlocfilehash: 7ce4262b3f32f48b61e6f4e273ce74c8334f8f0c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="public-c"></a>public (C++)
## <a name="syntax"></a>Syntaxe  
  
```  
public:  
   [member-list]  
public base-class  
```  
  
## <a name="remarks"></a>Remarques  
 Lorsqu’il précède une liste de membres de classe, le **public** mot clé indique que ces membres sont accessibles à partir de n’importe quelle fonction. Cela s'applique à tous les membres déclarés jusqu'au spécificateur d'accès suivant de la classe.  
  
 En faisant précéder le nom de classe de base, le **public** mot clé spécifie que les membres publics et protégés de la classe de base sont publics et les membres protégés, respectivement, de la classe dérivée.  
  
 L'accès par défaut des membres d'une classe est privé. L'accès par défaut des membres d'une structure ou d'une union est public.  
  
 L'accès par défaut d'une classe de base est privé pour les classes et public pour les structures. Les unions ne peuvent pas avoir de classes de base.  
  
 Pour plus d’informations, consultez [privé](../cpp/private-cpp.md), [protégé](../cpp/protected-cpp.md), [friend](../cpp/friend-cpp.md)et la table d’accès aux membres de [contrôle de l’accès aux membres de classe](member-access-control-cpp.md) .  
  
## <a name="clr-specific"></a>Spécifique /clr  
 Dans les types CLR, mots clés de spécificateur d’accès C++ (**public**, `private`, et `protected`) peuvent affecter la visibilité des types et méthodes quant aux assemblys. Pour plus d’informations, consultez [contrôle d’accès de membre](member-access-control-cpp.md).  
  
> [!NOTE]
>  Fichiers compilés avec [/LN](../build/reference/ln-create-msil-module.md) ne sont pas affectés par ce comportement. Dans ce cas, toutes les classes managées (public ou privées) seront visibles.  
  
## <a name="end-clr-specific"></a>Spécifique END /clr  
  
## <a name="example"></a>Exemple  
  
```  
// keyword_public.cpp  
class BaseClass {  
public:  
   int pubFunc() { return 0; }  
};  
  
class DerivedClass : public BaseClass {};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   aBase.pubFunc();       // pubFunc() is accessible   
                          //    from any function  
   aDerived.pubFunc();    // pubFunc() is still public in   
                          //    derived class  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de l’accès aux membres de classe](member-access-control-cpp.md)   
 [Mots clés](../cpp/keywords-cpp.md)
