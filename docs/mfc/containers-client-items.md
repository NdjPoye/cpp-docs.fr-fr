---
title: "Conteneurs&#160;: &#233;l&#233;ments clients | Microsoft Docs"
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
  - "éléments clients et conteneurs OLE"
  - "conteneurs OLE, éléments clients"
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs&#160;: &#233;l&#233;ments clients
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique ce que sont les éléments clients et de quelles classes votre application doit dériver ses éléments clients.  
  
 Les éléments clients sont les éléments appartenant à une autre application qui sont soit contenus soit référencés dans un document d'application de conteneur OLE.  Les éléments clients dont les données sont contenues dans le document sont incorporés ; ceux dont les données sont stockées dans un emplacement référencé par le document conteneur sont liés.  
  
 La classe de documents dans une application OLE est dérivée de la classe [COleDocument](../mfc/reference/coledocument-class.md) plutôt que de **CDocument**.  La classe `COleDocument` hérite de **CDocument** toutes les fonctionnalités nécessaires pour utiliser l'architecture documents\/Vue sur laquelle les applications de MFC sont basées.  `COleDocument` définit également une interface qui gère un document comme une collection d'objets `CDocItem`.  Plusieurs fonctions membres `COleDocument` sont fournies pour ajouter, récupérer, et supprimer les éléments de cette collection.  
  
 Chaque application conteneur doit dériver au moins une classe de `COleClientItem`.  Les objets de cette classe représentent les éléments, incorporés ou liés, dans le document OLE.  Ces objets existent pour la durée de vie du document les contenant, sauf s'ils sont supprimés du document.  
  
 `CDocItem` est la classe de base pour `COleClientItem` et `COleServerItem`.  Les objets des classes dérivées de ces deux agissent comme intermédiaires entre l'élément OLE et les applications clientes et serveur, respectivement.  Chaque fois qu'un nouveau OLE élément est ajouté au document, l'infrastructure MFC ajoute un objet d'une classe dérivée de `COleClientItem` de votre application cliente à la collection du document d'objets `CDocItem`.  
  
## Voir aussi  
 [Conteneurs](../mfc/containers.md)   
 [Conteneurs : fichiers composés](../mfc/containers-compound-files.md)   
 [Conteneurs : problèmes d'interface utilisateur](../mfc/containers-user-interface-issues.md)   
 [Conteneurs : fonctionnalités avancées](../mfc/containers-advanced-features.md)   
 [COleClientItem Class](../mfc/reference/coleclientitem-class.md)   
 [COleServerItem Class](../mfc/reference/coleserveritem-class.md)