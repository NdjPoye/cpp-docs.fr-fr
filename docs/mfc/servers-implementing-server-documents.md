---
title: "Serveurs&#160;: impl&#233;mentation de documents de serveur | Microsoft Docs"
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
  - "applications serveur OLE, gérer des documents de serveur"
  - "documents de serveur, implémenter"
  - "serveurs, documents de serveur"
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Serveurs&#160;: impl&#233;mentation de documents de serveur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les étapes que vous devez prendre pour implémenter correctement un document serveur si vous ne spécifiez pas l'option OLE de serveur dans l'utilitaire d'installation.  
  
#### Pour définir une classe de document serveur  
  
1.  Dériver la classe de document de `COleServerDoc` au lieu de **CDocument**.  
  
2.  Créez une classe du serveur dérivée de `COleServerItem`.  
  
3.  Implémentez la fonction membre `OnGetEmbeddedItem` de la classe de document serveur.  
  
     `OnGetEmbeddedItem` est appelée lorsque l'utilisateur d'une application conteneur crée ou modifie un élément incorporé.  Il doit retourner un seul élément représentant le document en entier.  Il doit s'agir d'un objet de la `COleServerItem`\- classe dérivée.  
  
4.  Remplacer la fonction membre `Serialize` pour sérialiser le contenu du document.  Vous n'avez pas besoin de sérialiser la liste des éléments du serveur sauf si vous les utilisez pour représenter des données natives au document.  Pour plus d'informations, consultez *implémenter des éléments de serveur* de l'article [Serveurs : Éléments du serveur](../mfc/servers-server-items.md).  
  
 Lorsqu'un document serveur est créé, l'environnement enregistre automatiquement le document avec les DLL du système OLE.  Cela permet aux DLL d'identifier les documents de serveur.  
  
 Pour plus d'informations, consultez [COleServerItem](../mfc/reference/coleserveritem-class.md) et [COleServerDoc](../mfc/reference/coleserverdoc-class.md) dans *Référence de Bibliothèque de Classes*.  
  
## Voir aussi  
 [Serveurs](../mfc/servers.md)   
 [Serveurs : éléments du serveur](../mfc/servers-server-items.md)   
 [Serveurs : implémentation d'un serveur](../mfc/servers-implementing-a-server.md)   
 [Serveurs : implémentations de fenêtres frame sur place](../mfc/servers-implementing-in-place-frame-windows.md)