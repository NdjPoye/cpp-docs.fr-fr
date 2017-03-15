---
title: "// Attributs, commentaire | Microsoft Docs"
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
  - "Attributs (commentaire dans des fichiers sources MFC)"
  - "commentaires, Attributs"
  - "fichiers sources MFC, Attributs (commentaire)"
  - "commentaire d'attributs publics"
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Attributs, commentaire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La section de `// Attributes` d'une déclaration de classe de MFC contient les attributs publics \(ou les propriétés\) de l'objet.  Il s'agit généralement de variables membres, ou le obtenir\/assembler s'exécute.  « Obtenir » et les fonctions « et » peuvent ne pas être virtuels.  Les fonctions « obtenir » sont généralement **const**, car dans la plupart des cas elles n'ont pas d'effets secondaires.  Les membres sont normalement publics ; les attributs protégés et privés sont généralement dans la section d'implémentation.  
  
 Dans la liste témoin de la classe `CStdioFile`, sous [Un exemple de commentaires](../mfc/an-example-of-the-comments.md), la liste inclut une variable membre, `m_pStream`.  La classe `CDC` répertorie environ 20 membres avec ce commentaire.  
  
> [!NOTE]
>  Les classes importantes, telles que `CDC` et `CWnd`, peuvent contenir tellement de membres qu'en répertoriant simplement tous les attributs à un groupe n'ajouterait peu de clarté.  Dans ce cas, la bibliothèque de classes utilise d'autres commentaires comme les titres pour effectuer davantage les membres.  Par exemple, `CDC` utilise `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`, et plus.  Les groupes qui représentent des attributs suivront la syntaxe décrite ci\-dessus habituelle.  De nombreuses OLE classes ont une section d'implémentation appelée `// Interface Maps`.  
  
## Voir aussi  
 [Utilisation des fichiers sources MFC](../mfc/using-the-mfc-source-files.md)   
 [Un exemple des commentaires](../mfc/an-example-of-the-comments.md)   
 [\/\/ Commentaire sur l'implémentation](../mfc/decrement-implementation-comment.md)   
 [\/\/ Constructeurs, commentaire](../mfc/decrement-constructors-comment.md)   
 [\/\/ Opérations, commentaires](../mfc/decrement-operations-comment.md)   
 [\/\/ Remplaçable, commentaire](../mfc/decrement-overridables-comment.md)