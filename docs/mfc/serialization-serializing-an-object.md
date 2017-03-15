---
title: "S&#233;rialisation&#160;: s&#233;rialisation d&#39;un objet | Microsoft Docs"
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
  - "objets (C++), sérialisation"
  - "sérialisation (C++), objets"
  - "sérialiser des objets (C++)"
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# S&#233;rialisation&#160;: s&#233;rialisation d&#39;un objet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'article [Sérialisation : Créer une classe sérialisable](../mfc/serialization-making-a-serializable-class.md) montre comment rendre une classe sérialisable.  Une fois que vous avez une classe sérialisable, vous pouvez sérialiser des objets de cette classe vers et à partir d'un fichier via un objet [CArchive](../mfc/reference/carchive-class.md).  Cet article explique :  
  
-   [Qu'est ce qu'un objet CArchive](../mfc/what-is-a-carchive-object.md).  
  
-   [deux manières de créer un objet CArchive](../mfc/two-ways-to-create-a-carchive-object.md).  
  
-   [Comment utiliser les opérateurs CArchive \<\< et \>\>](../mfc/using-the-carchive-output-and-input-operators.md).  
  
-   [Stockage et chargement de CObjects via une archive](../mfc/storing-and-loading-cobjects-via-an-archive.md)  
  
 Il est possible de laisser le framework créer l'archive pour votre document sérialisable ou créer explicitement l'objet `CArchive` vous\-même.  Vous pouvez transférer des données entre un fichier et l'objet sérialisable à l'aide des opérateurs \<\< et \>\> pour `CArchive` ou, dans certains cas, en appelant la fonction `Serialize` d'une classe dérivée de `CObject`.  
  
## Voir aussi  
 [Sérialisation](../mfc/serialization-in-mfc.md)