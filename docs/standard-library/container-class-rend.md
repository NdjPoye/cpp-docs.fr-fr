---
title: "Conteneur Class::rend | Microsoft Docs"
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
  - "rend (méthode)"
ms.assetid: 80f3dd04-dd2c-4b52-b0ed-d567ec5d186c
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Conteneur Class::rend
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique est dans la documentation Visual C\+\+ comme exemple fonctionnel de conteneurs utilisés dans la bibliothèque C\+\+ standard.  Pour plus d'informations, consultez l'[Conteneurs STL de](../standard-library/stl-containers.md).  
  
 La fonction retourne un membre itérateur inverse qui pointe vers le premier élément dans la séquence \(ou seulement au delà de la fin d'une séquence vide\), qui indique la fin de la séquence d'annulation.  
  
## Syntaxe  
  
```  
  
      const_reverse_iterator rend( ) const;   
reverse_iterator rend( );  
```  
  
## Voir aussi  
 [Exemple de conteneurs, classe](../standard-library/sample-container-class.md)