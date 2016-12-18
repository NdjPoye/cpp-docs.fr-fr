---
title: "MAPI | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
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
  - "messagerie électronique, activer"
  - "activer des applications pour messagerie électronique"
  - "activer des applications pour MAPI"
  - "message électronique, activer votre application"
  - "prise en charge MAPI dans les MFC"
  - "MAPI, MFC"
  - "messagerie, applications clientes"
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MAPI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique le Messaging Application Programming Interface \(MAPI\) Microsoft pour les développeurs d'applications de message client.  MFC fournit la prise en charge d'un sous\-ensemble MAPI de la classe **CDocument** mais n'inclut pas l'API entière.  Pour plus d'informations, consultez [MAPI Support in MFC](../mfc/mapi-support-in-mfc.md).  
  
 MAPI repose sur un ensemble de fonctions que les applications utilisant les courriers et les applications compatibles avec les courriers utilisent pour créer, manipuler, transférer, et pour stocker des messages électroniques.  Cela donne aux développeurs d'applications des outils pour définir l'objectif et le contenu des messages électroniques et leur offre une souplesse dans leur gestion des messages électroniques stockés.  MAPI fournit également une interface commune que les développeurs d'applications peuvent utiliser pour créer indépendamment des applications de système utilisant des mails et des applications compatibles avec les mails du système messagerie sous\-jacent.  
  
 Les clients de messagerie fournissent une interface humaine pour l'interaction entre le système de messagerie \(WMS\) Microsoft Windows.  Cette interaction comprend généralement des services de requête provenant des fournisseurs compatibles avec MAPI tels que des magasins d'informations et des livres d'adresses.  
  
 Pour plus d'informations sur l'interface MAPI, consultez les articles dans le guide de la messagerie Win32 \(MAPI\) du [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Dans cette section  
 [Prise en charge MAPI dans MFC](../mfc/mapi-support-in-mfc.md)  
  
## Voir aussi  
 [CDocument::OnFileSendMail](../Topic/CDocument::OnFileSendMail.md)   
 [CDocument::OnUpdateFileSendMail](../Topic/CDocument::OnUpdateFileSendMail.md)   
 [COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)