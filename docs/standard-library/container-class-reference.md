---
title: "Conteneur Class::reference | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reference (méthode)"
ms.assetid: ab85a9fb-c628-4761-9a5f-a0231fad7690
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Conteneur Class::reference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique est dans la documentation Visual C\+\+ comme exemple fonctionnel de conteneurs utilisés dans la bibliothèque C\+\+ standard.  Pour plus d'informations, consultez l'[Conteneurs STL de](../standard-library/stl-containers.md).  
  
 Décrit un objet qui peut servir de référence à un élément de la séquence contrôlée.  
  
## Syntaxe  
  
```  
  
typedef T2 reference;  
  
```  
  
## Notes  
 Il est décrit ici comme synonyme du type non spécifié **T2** \(généralement **Alloc::reference**\).  Objet de type **référence** peut être converti en un objet de type [const\_reference](../standard-library/container-class-const-reference.md).  
  
## Voir aussi  
 [Exemple de conteneurs, classe](../standard-library/sample-container-class.md)