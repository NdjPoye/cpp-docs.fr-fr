---
title: "Conteneur Class::rbegin | Microsoft Docs"
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
  - "rbegin (méthode)"
ms.assetid: c1f0d60c-93aa-4313-81b9-04e3f9c796c2
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Conteneur Class::rbegin
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique est dans la documentation Visual C\+\+ comme exemple fonctionnel de conteneurs utilisés dans la bibliothèque C\+\+ standard.  Pour plus d'informations, consultez l'[Conteneurs STL de](../standard-library/stl-containers.md).  
  
 Retourne un itérateur inverse qui pointe uniquement au delà de la fin de la séquence contrôlée, qui indique le début de la séquence d'annulation.  
  
## Syntaxe  
  
```  
const_reverse_iterator rbegin( ) const;  
reverse_iterator rbegin( );  
```  
  
## Voir aussi  
 [Exemple de conteneurs, classe](../standard-library/sample-container-class.md)