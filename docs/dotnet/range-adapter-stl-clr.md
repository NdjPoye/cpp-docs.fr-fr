---
title: "range_adapter (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::range_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "range_adapter (classe) (STL/CLR)"
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# range_adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe de modèle qui encapsule une paire d'itérateurs utilisés pour implémenter plusieurs interfaces de bibliothèque de classes de base \(BCL\).  Utilisez le range\_adapter pour manipuler une plage STL\/CLR comme s'il s'agissait d'une collection de BCL.  
  
## Syntaxe  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### Paramètres  
 Iter  
 Le type associé aux les itérateurs encapsulés.  
  
## Membres  
  
|Méthode|Description|  
|-------------|-----------------|  
|[range\_adapter::range\_adapter](../dotnet/range-adapter-range-adapter-stl-clr.md)|Construit un objet adaptateur.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[range\_adapter::operator\=](../dotnet/range-adapter-operator-assign-stl-clr.md)|Remplace la paire d'itérateurs stockés.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.Collections.IEnumerable>|Parcourt les éléments de la collection.|  
|<xref:System.Collections.ICollection>|Maintient un groupe d'éléments .|  
|<xref:System.Collections.Generic.IEnumerable%601>|Parcourt les éléments typés dans la collection.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintient un groupe d'éléments typés.|  
  
## Notes  
 Le range\_adapter enregistre une paire d'itérateurs, qui délimitent ensuite une séquence d'éléments.  L'objet implémente quatre interfaces de BCL qui vous permettent de parcourir les éléments, dans l'ordre.  Vous utilisez cette classe de modèle pour manipuler des plages STL\/CLR comme des conteneurs de BCL.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/adapter\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [collection\_adapter](../dotnet/collection-adapter-stl-clr.md)   
 [make\_collection](../dotnet/make-collection-stl-clr.md)