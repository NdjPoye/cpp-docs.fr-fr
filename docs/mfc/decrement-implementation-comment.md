---
title: "// Commentaire sur l&#39;impl&#233;mentation | Microsoft Docs"
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
  - "commentaires, commentaires sur l'implémentation"
  - "commentaires, MFC"
  - "commentaire sur l'implémentation dans des fichiers sources MFC"
  - "fichiers sources MFC, commentaire sur l'implémentation"
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Commentaire sur l&#39;impl&#233;mentation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La section `// Implementation` est la partie la plus importante de toute déclaration de classe MFC.  
  
 Cette section regroupe tous les détails d'implémentation.  Les attributs et les méthodes peuvent apparaître dans cette section.  Tout en dessous de cette ligne peut changer dans une version ultérieure de MFC.  À moins que vous ne puissiez pas l'éviter, vous ne devez pas compter sur les détails sous la ligne `// Implementation`.  En outre, les membres déclarés sous la ligne d'implémentation ne sont pas documentés, bien que certaines implémentations soient discutées dans des notes techniques.  Les substitutions des fonctions virtuelles dans la classe de base résident dans cette section, indépendamment de la section où la fonction de la classe de base, parce que le fait qu'une fonction remplace l'implémentation de la classe de base est considéré comme un détail d'implémentation.  En général, ces membres sont protégés, mais pas toujours.  
  
 Note de la liste `CStdioFile` sous [Un exemple de commentaires](../mfc/an-example-of-the-comments.md) que les membres déclarés sous le commentaire `// Implementation` peuvent être déclarés comme **public**, `protected`, ou `private`.  Vous devez utiliser ces membres avec précaution, car ils peuvent changer à l'avenir.  La déclaration d'un groupe de membres comme **public** peut être nécessaire pour que l'implémentation de la bibliothèque de classes fonctionne correctement.  Toutefois, cela ne signifie pas que vous pouvez utiliser en toute sécurité les membres déclarés ainsi.  
  
> [!NOTE]
>  Vous pouvez rechercher les commentaires des types restants au\-dessus ou en dessous du commentaire `// Implementation`.  Dans l'un et l'autre cas, ils décrivent les types de membres déclarés en dessous.  S'ils apparaissent sous le commentaire `// Implementation`, vous devez supposer que les membres peuvent changer dans les versions ultérieures de MFC.  
  
## Voir aussi  
 [Utilisation des fichiers sources MFC](../mfc/using-the-mfc-source-files.md)   
 [Un exemple des commentaires](../mfc/an-example-of-the-comments.md)   
 [\/\/ Constructeurs, commentaire](../mfc/decrement-constructors-comment.md)   
 [\/\/ Attributs, commentaire](../mfc/decrement-attributes-comment.md)   
 [\/\/ Opérations, commentaires](../mfc/decrement-operations-comment.md)   
 [\/\/ Remplaçable, commentaire](../mfc/decrement-overridables-comment.md)