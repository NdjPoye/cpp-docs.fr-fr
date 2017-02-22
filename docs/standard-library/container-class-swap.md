---
title: "Conteneur Class::swap | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap (méthode)"
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Conteneur Class::swap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique est dans la documentation Visual C\+\+ comme exemple fonctionnel de conteneurs utilisés dans la bibliothèque C\+\+ standard.  Pour plus d'informations, consultez l'[Conteneurs STL de](../standard-library/stl-containers.md).  
  
 Habite les séquences réorganisées entre **\*this** et `_Right`.  
  
## Syntaxe  
  
```  
  
      void swap(  
   Container& _Right  
);  
```  
  
## Notes  
 Si **get\_allocator \=\=** `_Right`**.get\_allocator**, il fait dans le temps fixe.  Sinon, il exécute plusieurs affectations d'élément et le constructeur appelle proportionnel au nombre d'éléments dans les séquences contrôlées.  
  
## Voir aussi  
 [Exemple de conteneurs, classe](../standard-library/sample-container-class.md)