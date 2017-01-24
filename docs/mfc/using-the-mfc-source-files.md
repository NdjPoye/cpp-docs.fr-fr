---
title: "Utilisation des fichiers sources MFC | Microsoft Docs"
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
  - "commentaires, MFC"
  - "fichiers sources MFC"
  - "MFC, fichiers sources"
  - "accès aux membres privés"
  - "accès aux membres protégés"
  - "membres publics"
  - "fichiers sources"
  - "fichiers sources, MFC"
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des fichiers sources MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque Microsoft Foundation Class \(MFC\) fournit du code source complet.  Les fichiers d'en\-tête \(.h\) se trouvent dans le répertoire \\atlmf\\inclure; les fichiers d'implémentation \(.cpp\) se trouvent dans le répertoire \\atlmfc\\src\\mfc.  
  
 Cette famille d'articles décrit les conventions que MFC utilise pour commenter les différentes parties de chaque classe, la signification de ces commentaires, ainsi que ce que vous devriez vous attendre à trouver dans chaque section.  Les assistants Visual C\+\+ utilisent des conventions semblables aux classes qu'ils créent automatiquement, et vous trouverez peut\-être ces conventions utiles pour votre propre code.  
  
 Vous connaissez peut\-être les mots clé C\+\+ **public**, d' `protected`, et les mots clés d' `private` .  En examinant les fichiers d'en\-tête de MFC, vous constaterez que chaque classe peut en avoir plusieurs.  Par exemple, les variables membres et les fonctions publiques peuvent être sous plusieurs mot clé de **public**.  Cela est dû au fait que MFC sépare les variables de membre et les fonctions en fonction de leur utilisation, et non par le type d'accès autorisé.  MFC utilise `private` avec parcimonie; même les éléments considérés comme des détails d'implémentation sont généralement protégés et beaucoup de temps sont publics.  Bien que l'accès aux détails d'implémentation est découragé, MFC vous laisse la prise de décision.  
  
 Dans les fichiers sources de MFC et les fichiers que l'Assistant d'Application MFC crée, vous trouverez des commentaires comme ces derniers dans des déclarations de classe \(généralement dans cet ordre\) :  
  
 `// Constructors`  
  
 `// Attributes`  
  
 `// Operations`  
  
 `// Overridables`  
  
 `// Implementation`  
  
 Les rubriques traitées dans cette famille d'articles sont les suivantes :  
  
-   [Un exemple des commentaires](../mfc/an-example-of-the-comments.md)  
  
-   [Le \/\/ Commentaire sur l'implémentation](../mfc/decrement-implementation-comment.md)  
  
-   [Le \/\/ commentaire de constructeurs](../mfc/decrement-constructors-comment.md)  
  
-   [Le \/\/ commentaire sur les attributs](../mfc/decrement-attributes-comment.md)  
  
-   [Le commentaire sur les opérations \/\/](../mfc/decrement-operations-comment.md)  
  
-   [Le \/\/ commentaire sur les substituables](../mfc/decrement-overridables-comment.md)  
  
## Voir aussi  
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)