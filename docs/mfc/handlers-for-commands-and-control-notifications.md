---
title: "Gestionnaires pour les commandes et les notifications de contr&#244;le | Microsoft Docs"
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
  - "commandes, gestionnaires pour"
  - "contrôles (MFC), notifications"
  - "fonctions (C++), gestionnaire"
  - "gestionnaires"
  - "gestionnaires, commande"
  - "gestionnaires, notification de contrôle"
  - "notifications, gestionnaires pour le contrôle"
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Gestionnaires pour les commandes et les notifications de contr&#244;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il n'y a aucun gestionnaire par défaut des commandes ou des messages de notification de contrôle.  Par conséquent, seule la convention vous impose d'affectater des noms pour les gestionnaires pour ces catégories de messages.  Lorsque vous mappez la notification de commandement ou de contrôle à un gestionnaire, les fenêtres Propriétés proposent un nom selon le code d'ID de commande ou de contrôle notification.  Vous pouvez accepter le nom proposé, le modifier, ou remplacer.  
  
 La convention suggère que vous nommiez les gestionnaires des deux catégories de l'objet interface utilisateur qu'ils représentent.  Ainsi un gestionnaire pour la commande Couper dans le menu Edition peut être nommé  
  
 [!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/CPP/handlers-for-commands-and-control-notifications_1.h)]  
  
 Étant donné que la commande Couper est si souvent implémentée dans les applications, le framework prédéfinit l'ID de commande pour la commande de secteur comme **ID\_EDIT\_CUT**.  Pour obtenir la liste de tous les ID de commande prédéfinis, consultez le fichier AFXRES.H.  Pour plus d'informations sur les commandes, consultez [Standard Commands](../mfc/standard-commands.md).  
  
 En outre, la convention propose qu'un gestionnaire pour le message de notification **BN\_CLICKED** à partir d'un bouton intitulé « my bouton » peut être nommé.  
  
 [!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/CPP/handlers-for-commands-and-control-notifications_2.h)]  
  
 Vous pouvez affecter à cette commande un ID de`IDC_MY_BUTTON` car il correspond à un objet d'interface utilisateur spécifique à l'application.  
  
 Les deux catégories de messages ne prennent aucun argument et ne retournent aucune valeur.  
  
## Voir aussi  
 [Déclaration des fonctions de gestionnaire de messages](../mfc/declaring-message-handler-functions.md)