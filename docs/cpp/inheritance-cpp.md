---
title: "H&#233;ritage (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), dérivés"
  - "classes dérivées"
  - "classes dérivées, à propos des classes dérivées"
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# H&#233;ritage (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette section explique comment utiliser les classes dérivées pour générer des programmes extensibles.  
  
## Vue d'ensemble  
 De nouvelles classes peuvent être dérivées de classes existantes à l'aide d'un mécanisme appelé Héritage \(pour plus d'informations, consultez pour commencer [Héritage simple](../cpp/single-inheritance.md)\).  Les classes utilisées pour la dérivation sont appelées classes de base d'une classe dérivée particulière.  Une classe dérivée est déclarée en utilisant la syntaxe suivante :  
  
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
  
 Après la balise \(nom\) de la classe, un signe deux\-points apparaît, suivi d'une liste de spécifications de base.  Les classes de base ainsi nommées doivent avoir été déclarées précédemment.  Les spécifications de base peuvent contenir un spécificateur d'accès, qui est l'un des mots clés **public**, `protected` ou `private`.  Ces spécificateurs d'accès apparaissent avant le nom de classe de base et s'appliquent uniquement à cette classe de base.  Ces spécificateurs contrôlent l'autorisation de la classe dérivée à utiliser pour les membres de la classe de base.  Pour plus d'informations sur l'accès aux membres de classe de base, consultez [Contrôle d'accès aux membres](../cpp/member-access-control-cpp.md).  Si le spécificateur d'accès est omis, l'accès à cette base est considéré comme `private`.  Les spécifications de base peuvent contenir le mot clé **virtual** pour indiquer l'héritage virtuel.  Ce mot clé peut apparaître avant ou après le spécificateur d'accès, le cas échéant.  Si l'héritage virtuel est utilisé, la classe de base est appelée classe de base virtuelle.  Pour plus d'informations, consultez [Classes de base virtuelles](../misc/virtual-base-classes.md).  
  
 Plusieurs classes de base peuvent être spécifiées en les séparant par des virgules.  Si une seule classe de base est spécifiée, le modèle d'héritage est appelé [Héritage simple](../cpp/single-inheritance.md). Si plusieurs classes de base sont spécifiées, le modèle d'héritage est appelé [Héritage multiple](http://msdn.microsoft.com/fr-fr/3b74185e-2beb-4e29-8684-441e51d2a2ca),  
  
 Les rubriques suivantes sont incluses :  
  
-   [Héritage simple](../cpp/single-inheritance.md)  
  
-   [Héritage multiple](http://msdn.microsoft.com/fr-fr/3b74185e-2beb-4e29-8684-441e51d2a2ca)  
  
-   [Plusieurs classes de base](../cpp/multiple-base-classes.md)  
  
-   [Classes de base virtuelles](../misc/virtual-base-classes.md)  
  
-   [Fonctions virtuelles](../cpp/virtual-functions.md)  
  
-   [Substitutions explicites](../cpp/explicit-overrides-cpp.md)  
  
-   [Classes abstraites](../cpp/abstract-classes-cpp.md)  
  
-   [Résumé des règles de portée](../cpp/summary-of-scope-rules.md)  
  
 Les mots clés [\_\_super](../cpp/super.md) et [\_\_interface](../cpp/interface.md) sont décrits dans cette section.  
  
## Voir aussi  
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)