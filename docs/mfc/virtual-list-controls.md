---
title: "Contr&#244;les de liste virtuels | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "cache, données d'éléments de contrôles de liste virtuels"
  - "contrôles de liste, Liste (vue)"
  - "contrôles de liste, virtuels"
  - "contrôles de liste virtuels"
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les de liste virtuels
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contrôle de liste virtuel est un contrôle de liste d'affichage qui contient le style de **LVS\_OWNERDATA**.  Ce style permet au contrôle de prendre en charge un nombre d'éléments jusqu'à `DWORD` \(le nombre d'éléments par défaut s'étend uniquement à `int`\).  Toutefois, le plus grand avantage offert par ce style est la capacité d'avoir uniquement un sous\-ensemble d'éléments de données en mémoire en même temps.  Cela permet au contrôle de liste d'affichage virtuel de se prêter à utilisation avec de grandes bases de données d'informations, où les méthodes spécifiques d'accéder aux données sont déjà en place.  
  
> [!NOTE]
>  En plus de fournir des fonctionnalités de liste virtuelle dans `CListCtrl`, MFC fournit également la même fonctionnalité que la classe d' [CListView](../mfc/reference/clistview-class.md).  
  
 Il existe des problèmes de compatibilité connus que vous devez connaître lors du développement des contrôles de liste virtuels.  Pour plus d'informations, consultez la section des problèmes de compatibilité de la rubrique de contrôle d'affichage de liste dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Gérer la notification de LVN\_GETDISPINFO  
 Les contrôles de liste virtuels contiennent des très peu d'informations sur les éléments.  Hormis la sélection d'éléments et l'information de focus, toutes les informations d'élément sont gérées par le propriétaire du contrôle.  Les informations sont demandées par l'infrastructure via un message de notification de **LVN\_GETDISPINFO**.  Pour fournir les informations demandées, le propriétaire du contrôle de liste virtuel \(ou le contrôle lui\-même\) doit traiter cette notification.  Cela peut facilement être effectuée à l'aide de la fenêtre Propriétés \(voir [Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md)\).  Le code obtenu doit ressembler à quelque chose comme l'exemple suivant \(où `CMyDialog` détient l'objet de contrôle de liste virtuel et la boîte de dialogue gère la notification\) :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/CPP/virtual-list-controls_1.cpp)]  
  
 Dans le gestionnaire du message de notification de **LVN\_GETDISPINFO**, vous devez voir quels types d'informations sont demandés.  Les valeurs possibles sont :  
  
-   `LVIF_TEXT` Le membre d' `pszText` doit être rempli.  
  
-   `LVIF_IMAGE` Le membre d' `iImage` doit être rempli.  
  
-   **LVIF\_INDENT** Le membre *iIndent* doit être rempli.  
  
-   `LVIF_PARAM` Le membre *de lParam* doit être rempli. \(Pas présent pour les sous\-articles.\)  
  
-   `LVIF_STATE` Le membre de l' *état*  doit être rempli.  
  
 Vous devez alors fournir n'importe quelles informations demandées à l'infrastructure.  
  
 L'exemple suivant \(pris du corps du gestionnaire de notification de l'objet de contrôle de liste\) illustre une méthode possible en fournissant des informations sur les mémoires tampons de texte et image d'un élément :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/CPP/virtual-list-controls_2.cpp)]  
  
## La mise en cache et contrôles de liste virtuels  
 Étant donné que ce type de contrôle de liste est destiné à des jeux de données volumineux, il est recommandé de mettre en cache les données demandées d'élément pour améliorer les performances de récupération.  L'infrastructure fournit un mécanisme de cache\-hinting sans indication d'aide en optimisant le cache en envoyant un message de notification de **LVN\_ODCACHEHINT**.  
  
 L'exemple suivant met à jour le cache avec la plage passée à la fonction gestionnaire.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/CPP/virtual-list-controls_3.cpp)]  
  
 Pour plus d'informations sur la préparation et entretien d'un cache, consultez la section " gestion du cache de la rubrique de contrôle d'affichage de liste dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Rechercher des éléments spécifiques  
 Le message de notification de **LVN\_ODFINDITEM** est envoyé par le contrôle de liste virtuel lorsqu'un élément particulier de contrôle de liste doit être trouvé.  Le message de notification est envoyé lorsque le contrôle d'affichage de liste a un accès rapide principal ou lorsqu'il reçoit un message de **LVM\_FINDITEM**.  Les informations de recherche sont envoyées sous la forme d'une structure de **LVFINDINFO**, qui est membre de la structure de **NMLVFINDITEM**.  Traitez ce message en substituant la fonction d' `OnChildNotify` de votre objet de contrôle de liste et à l'intérieur du corps du responsable, recherchez le message de **LVN\_ODFINDITEM**.  Le cas échéant, exécutez l'action appropriée.  
  
 Vous devez être prêt à rechercher un élément correspondant aux informations fournies par le contrôle d'affichage de liste.  Vous devez retourner l'index de l'élément en cas de réussite, ou \-1 si aucun élément correspondant n'a été trouvé.  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)