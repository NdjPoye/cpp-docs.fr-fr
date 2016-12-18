---
title: "Serveurs de documents actifs | Microsoft Docs"
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
  - "serveurs de documents actifs (C++)"
  - "documents actifs (C++), serveurs"
  - "serveurs (C++), document actif"
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Serveurs de documents actifs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Serveurs de documents actifs tels que les documents Word, Excel, ou PowerPoint hôtes d'autres types d'application appelés documents hôtes.  Contrairement aux objets incorporés OLE \(qui sont simplement affichés dans la page d'un autre document\), les documents actifs fournissent l'interface complète et complètent des fonctionnalités natives de l'application serveur qui les crée.  Les utilisateurs peuvent créer des documents en utilsant la pleine puissance de leurs applications favorites \(s'ils ont activé les documents actifs\), mais peuvent traiter le projet résultant comme une entité unique.  
  
 Les documents actifs peuvent avoir plusieurs pages et sont toujours actifs sur place.  Partie de contrôle des documents actifs de l'interface utilisateur, fusionnant les menus et les menus **Fichier** et **Aide** du conteneur.  Ils occupent la zone de modification entière du conteneur et contrôlent les vues et la mise en page d'imprimantes \(marges, pieds de page, et ainsi de suite\).  
  
 MFC implémente des serveurs de documents actifs avec les interfaces de documents\/vue, les tables de dispatch de commande, l'impression, la gestion des menus, et la gestion de Registre.  Les critères spécifiques de rgramation requis sont décrits dans [documents actifs](../mfc/active-documents.md).  
  
 MFC supporte les documents actifs avec la classe[CDocObjectServer](../mfc/reference/cdocobjectserver-class.md), dérivée de [CCmdTarget](../mfc/reference/ccmdtarget-class.md), et de [CDocObjectServerItem](../mfc/reference/cdocobjectserveritem-class.md), dérivée de [COleServerItem](../mfc/reference/coleserveritem-class.md).  MFC supporte les conteneurs de documents actifs avec la classe [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md), dérivée de [COleClientItem](../mfc/reference/coleclientitem-class.md).  
  
 `CDocObjectServer` mappe les interfaces de document actif et initialise et active un document actif.  MFC fournit également des macros pour gérer le routage des commandes des documents actifs.  Pour utiliser des documents actifs dans votre application, incluez AfxDocOb.h dans votre fichier de StdAfx.h.  
  
 Un serveur MFC normal installe sa propre classe dérivée `COleServerItem`.  L'Application MFC génère cette classe pour vous si vous activez la case à cocher **Mini\-server** ou **Full\-server** pour permettre au serveur d'applications la prise en charge du document composite.  Si vous activez également la case à cocher **Serveur de documents actifs**, l'Application MFC génère une classe dérivée de `CDocObjectServerItem` à la place.  
  
 La classe `COleDocObjectItem` permet à un conteneur OLE de devenir un conteneur de documents actifs.  Vous pouvez utiliser l'Application MFC pour créer un conteneur de documents actifs en activant la case à cocher de **Conteneur de documents actifs** dans la page de prise en charge du document composé de l'Application MFC.  Pour plus d'informations, consultez [Créer une application de conteneur de documents actifs](../mfc/creating-an-active-document-container-application.md).  
  
## Voir aussi  
 [Relation contenant\-contenu de document actif](../mfc/active-document-containment.md)