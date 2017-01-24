---
title: "Serveurs&#160;: impl&#233;mentation d&#39;un serveur | Microsoft Docs"
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
  - "applications serveur OLE, implémenter des serveurs OLE"
  - "serveurs, implémenter"
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Serveurs&#160;: impl&#233;mentation d&#39;un serveur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique le code de l'Application MFC la création d'une application serveur de modification sur place.  Si vous n'utilisez pas l'Application, les listes de cet article les zones où vous devez écrire du code pour implémenter une application serveur.  
  
 Si vous utilisez l'Application pour créer une application serveur, il fournit une quantité importante de code spécifique au serveur pour vous.  Si vous ajoutez la fonctionnalité de serveur de modification sur place à une application existante, vous devez dupliquer code qu'aurait l'Application fourni avant d'ajouter le reste de codes du serveur nécessaire.  
  
 Le serveur auquel l'Application fournit des ranger en plusieurs catégories :  
  
-   Définir les ressources du serveur  
  
    -   La ressource menu utilisée lorsque le serveur est un élément incorporé dans sa propre fenêtre.  
  
    -   Les ressources de menu et la barre d'outils utilisées lorsque le serveur est en place actif.  
  
     Pour plus d'informations sur ces ressources, consultez [Menus et de ressources : Ajouts de serveur](../mfc/menus-and-resources-server-additions.md).  
  
-   Définition d'une classe d'élément issue de `COleServerItem`.  Pour obtenir plus de détails sur les éléments du serveur, consultez [Serveurs : Éléments du serveur](../mfc/servers-server-items.md).  
  
-   Modifier la classe de base de la classe de document à `COleServerDoc`.  Pour obtenir plus de détails, consultez [Serveurs : Implémenter des documents de serveur](../mfc/servers-implementing-server-documents.md).  
  
-   Définition d'une classe d'affichage cadre dérivée de `COleIPFrameWnd`.  Pour obtenir plus de détails, consultez [Serveurs : Implémentation d'autres cadres sur place](../mfc/servers-implementing-in-place-frame-windows.md).  
  
-   Création d'une entrée pour l'application serveur la base de données d'inscription de Windows et en enregistrant la nouvelle instance du serveur avec OLE le système.  Pour plus d'informations sur cette rubrique, consultez [Registration](../mfc/registration.md).  
  
-   Initialisation et lançant l'application serveur.  Pour plus d'informations sur cette rubrique, consultez [Registration](../mfc/registration.md).  
  
 Pour plus d'informations, consultez [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md), et [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) dans *Référence de Bibliothèque de Classes*.  
  
## Voir aussi  
 [Serveurs](../mfc/servers.md)   
 [Conteneurs](../mfc/containers.md)   
 [Menus et ressources \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [Inscription](../mfc/registration.md)