---
title: "Conteneur Class::erase | Microsoft Docs"
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
  - "erase (méthode)"
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Conteneur Class::erase
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique est dans la documentation Visual C\+\+ comme exemple fonctionnel de conteneurs utilisés dans la bibliothèque C\+\+ standard.  Pour plus d'informations, consultez l'[Conteneurs STL de](../standard-library/stl-containers.md).  
  
 Efface un élément.  
  
## Syntaxe  
  
```  
  
      iterator erase(  
   iterator _Where   
);  
iterator erase(  
   iterator _First,  
   iterator _Last   
);  
```  
  
## Notes  
 La première fonction membre supprime l'élément de la séquence contrôlée désignée par le  \_*Where***.** La deuxième fonction membre supprime les éléments de la séquence contrôlée dans la plage \[`_First`, `_Last`\).  Les deux retournent un itérateur qui indique le premier élément restant au delà de tous les éléments supprimés, ou [end](../standard-library/container-class-end.md) si aucun ce élément n'existe.  
  
 Les fonctions membres lèvent une exception si une opération de copie lève une exception.  
  
## Voir aussi  
 [Exemple de conteneurs, classe](../standard-library/sample-container-class.md)