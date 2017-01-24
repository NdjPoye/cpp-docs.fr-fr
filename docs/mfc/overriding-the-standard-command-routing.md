---
title: "Substitution du routage des commandes standard | Microsoft Docs"
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
  - "gestion des commandes, router des commandes"
  - "routage des commandes, substituer"
  - "MFC, routage des commandes"
  - "substituer, routage des commandes standard"
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Substitution du routage des commandes standard
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans de rares cas où vous devez implémenter une certaine variante de l'infrastructure standard de routage, vous pouvez le remplacer.  L'idée consiste à modifier le routage dans une ou plusieurs classes en remplaçant le `OnCmdMsg` de ces classes.  Procédez ainsi :  
  
-   Dans la classe qui désactive la commande à transmettre à un objet différent.  
  
-   Dans le nouvel objet non par défaut ou dans les commandes à des cibles auxquelles il pourrait ensuite passer des commandes.  
  
 Si vous insérez un certain objet dans le routage, la classe doit être une classe cible de la commande.  Dans les versions substituantes de `OnCmdMsg`, veillez à appeler la version que vous substituez.  Consultez la méthode [OnCmdMsg](../Topic/CCmdTarget::OnCmdMsg.md) de la classe `CCmdTarget` dans *le guide de MFC* et les versions des classes telles que `CView` et **CDocument** dans le code source fourni, pour des exemples.  
  
## Voir aussi  
 [Méthode d'appel d'un gestionnaire par le Framework](../mfc/how-the-framework-calls-a-handler.md)