---
title: Private (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- private_cpp
dev_langs:
- C++
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb0b8c748a3cf92faae451ab024d5592bb24b47
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="private-c"></a>private (C++)
## <a name="syntax"></a>Syntaxe  
  
```  
private:  
   [member-list]  
private base-class  
```  
  
## <a name="remarks"></a>Notes  
 Lorsqu'il précède une liste de membres de classe, le mot clé `private` indique que ces membres sont accessibles à partir de n'importe quelle fonction et friends de la classe. Cela s'applique à tous les membres déclarés jusqu'au spécificateur d'accès suivant de la classe.  
  
 En faisant précéder le nom d'une classe de base, le mot clé `private` indique que les membres publics et protégés de la classe de base sont des membres privés de la classe dérivée.  
  
 L'accès par défaut des membres d'une classe est privé. L'accès par défaut des membres d'une structure ou d'une union est public.  
  
 L'accès par défaut d'une classe de base est privé pour les classes et public pour les structures. Les unions ne peuvent pas avoir de classes de base.  
  
 Pour plus d’informations, consultez [friend](../cpp/friend-cpp.md), [public](../cpp/public-cpp.md), [protégé](../cpp/protected-cpp.md)et la table d’accès aux membres de [contrôle de l’accès aux membres de classe](member-access-control-cpp.md).  
  
## <a name="clr-specific"></a>Spécifique /clr  
 Dans les types CLR, mots clés de spécificateur d’accès C++ (**public**, `private`, et `protected`) peuvent affecter la visibilité des types et méthodes quant aux assemblys. Pour plus d’informations, consultez [contrôle d’accès de membre](member-access-control-cpp.md).  
  
> [!NOTE]
>  Fichiers compilés avec [/LN](../build/reference/ln-create-msil-module.md) ne sont pas affectés par ce comportement. Dans ce cas, toutes les classes managées (public ou privées) seront visibles.  
  
## <a name="end-clr-specific"></a>Spécifique END /clr  
  
## <a name="example"></a>Exemple  
  
```  
// keyword_private.cpp  
class BaseClass {  
public:  
   // privMem accessible from member function  
   int pubFunc() { return privMem; }  
private:  
   void privMem;  
};  
  
class DerivedClass : public BaseClass {  
public:  
   void usePrivate( int i )  
      { privMem = i; }   // C2248: privMem not accessible  
                         // from derived class  
};  
  
class DerivedClass2 : private BaseClass {  
public:  
   // pubFunc() accessible from derived class  
   int usePublic() { return pubFunc(); }  
};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   DerivedClass2 aDerived2;  
   aBase.privMem = 1;     // C2248: privMem not accessible  
   aDerived.privMem = 1;  // C2248: privMem not accessible  
                          //    in derived class  
   aDerived2.pubFunc();   // C2247: pubFunc() is private in  
                          //    derived class  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de l’accès aux membres de classe](member-access-control-cpp.md)   
 [Mots clés](../cpp/keywords-cpp.md)