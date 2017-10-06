---
title: "Héritage (C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- derived classes [C++]
- derived classes [C++], about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
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
ms.openlocfilehash: dba45acbc602465db876038e83cb0cd496b2337e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="inheritance--c"></a>Héritage (C++)
Cette section explique comment utiliser les classes dérivées pour générer des programmes extensibles.  
  
## <a name="overview"></a>Vue d'ensemble  
 Nouvelles classes peuvent être dérivés de classes existantes à l’aide d’un mécanisme appelé « héritage » (consultez le début des informations de [l’héritage unique](../cpp/single-inheritance.md)). Les classes utilisées pour la dérivation sont appelées classes de base d'une classe dérivée particulière. Une classe dérivée est déclarée en utilisant la syntaxe suivante :  
  
```  
 class Derived : [virtual] [access-specifier] Base  
{  
   // member list  
};  
 class Derived : [virtual] [access-specifier] Base1,  
 [virtual] [access-specifier] Base2, . . .  
{  
   // member list  
};  
```  
  
 Après la balise (nom) de la classe, un signe deux-points apparaît, suivi d'une liste de spécifications de base.  Les classes de base ainsi nommées doivent avoir été déclarées précédemment.  Les spécifications de base peuvent contenir un spécificateur d’accès, qui est un des mots clés **public**, `protected` ou `private`.  Ces spécificateurs d'accès apparaissent avant le nom de classe de base et s'appliquent uniquement à cette classe de base.  Ces spécificateurs contrôlent l'autorisation de la classe dérivée à utiliser pour les membres de la classe de base.  Consultez [le contrôle d’accès de membre](../cpp/member-access-control-cpp.md) pour plus d’informations sur l’accès aux membres de la classe de base.  Si le spécificateur d'accès est omis, l'accès à cette base est considéré comme `private`.  Les spécifications de base peuvent contenir le mot clé **virtuels** pour indiquer l’héritage virtuel.  Ce mot clé peut apparaître avant ou après le spécificateur d'accès, le cas échéant.  Si l'héritage virtuel est utilisé, la classe de base est appelée classe de base virtuelle.  
  
 Plusieurs classes de base peuvent être spécifiées en les séparant par des virgules.  Si une seule classe de base est spécifiée, le modèle d’héritage est [unique d’héritage](../cpp/single-inheritance.md). Si plusieurs classes de base est spécifié, le modèle d’héritage est appelé [l’héritage Multiple](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca),  
  
 Les rubriques suivantes sont incluses :  
  
-   [Héritage simple](../cpp/single-inheritance.md)  
  
-   [Héritage multiple](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca)  
  
-   [Plusieurs classes de base](../cpp/multiple-base-classes.md)  
  
-   [Fonctions virtuelles](../cpp/virtual-functions.md)  
  
-   [Substitutions explicites](../cpp/explicit-overrides-cpp.md)  
  
-   [Classes abstraites](../cpp/abstract-classes-cpp.md)  
  
-   [Résumé des règles de portée](../cpp/summary-of-scope-rules.md)  
  
 Le [__super](../cpp/super.md) et [__interface](../cpp/interface.md) mots clés sont décrits dans cette section.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur le langage C++](../cpp/cpp-language-reference.md)
