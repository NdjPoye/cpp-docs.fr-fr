---
title: "// Constructeurs, commentaire | Microsoft Docs"
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
  - "commentaires, constructeurs (commentaire)"
  - "commentaires, MFC"
  - "constructeurs [C++], déclarer"
  - "constructeurs (commentaire)"
  - "déclarations, constructeurs"
  - "déclarer des constructeurs, commentaires de code"
  - "constructeurs d'instance, commentaires de code"
  - "fichiers sources MFC, Constructeurs (commentaire)"
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Constructeurs, commentaire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La section d'`// Constructors` d'une déclaration de classe de MFC déclare des constructeurs \(dans le sens C\+\+\) ainsi que toutes les fonctions d'initialisation requises pour utiliser réellement l'objet.  Par exemple, `CWnd::Create` dans la section de constructeurs car avant d'utiliser l'objet d'`CWnd`, il doit être « entièrement construit » en appelant d'abord le constructeur C\+\+ et en appelant après la fonction de **Créer**.  En général, les membres sont publics.  
  
 Par exemple, la classe d'`CStdioFile` a trois constructeurs, l'un d'eux est illustrée dans la liste sous [Un exemple de commentaires](../mfc/an-example-of-the-comments.md).  
  
## Voir aussi  
 [Utilisation des fichiers sources MFC](../mfc/using-the-mfc-source-files.md)   
 [\/\/ Commentaire sur l'implémentation](../mfc/decrement-implementation-comment.md)   
 [\/\/ Attributs, commentaire](../mfc/decrement-attributes-comment.md)   
 [\/\/ Opérations, commentaires](../mfc/decrement-operations-comment.md)   
 [\/\/ Remplaçable, commentaire](../mfc/decrement-overridables-comment.md)