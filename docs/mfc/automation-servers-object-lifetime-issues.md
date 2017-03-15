---
title: "Serveurs Automation&#160;: probl&#232;mes li&#233;s &#224; la dur&#233;e de vie des objets | Microsoft Docs"
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
  - "Automation (serveurs), durée de vie des objets"
  - "durée de vie, serveur d'Automation"
  - "objets (C++), durée de vie"
  - "serveurs, durée de vie d'Automation"
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Serveurs Automation&#160;: probl&#232;mes li&#233;s &#224; la dur&#233;e de vie des objets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un client Automation crée ou active un élément OLE, le serveur passe au client un pointeur vers cet objet.  Le client établit une référence à l'objet par un appel à la fonction OLE [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379).  Cette référence est en vigueur tant que le client appelle [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317). \(Les applications clientes écrites avec les classes OLE de la bibliothèque Microsoft Foundation Class n'ont pas besoin d'effectuer ces appels ; l'infrastructure s'en charge.\) Le système OLE et le serveur lui\-même peuvent générer des références à l'objet.  Un serveur ne doit pas détruire un objet tant que les références externes à l'objet reste active.  
  
 L'infrastructure maintient un décompte interne du nombre de références à un objet serveur dérivé [CCmdTarget](../mfc/reference/ccmdtarget-class.md).  Ce nombre est mis à jour lorsqu'un client Automation ou une autre entité ajoute ou libère une référence à l'objet.  
  
 Lorsque le nombre de références est 0, l'infrastructure appelle la fonction virtuelle [CCmdTarget::OnFinalRelease](../Topic/CCmdTarget::OnFinalRelease.md).  L'implémentation par défaut de la fonction appelle l'opérateur **delete** pour supprimer cet objet.  
  
 La bibliothèque MFC fournit des fonctionnalités supplémentaires pour contrôler le comportement de l'application lorsque les clients externes contiennent des références aux objets de l'application.  En plus de maintenir un décompte des références à chaque objet, les serveurs contiennent un compte global des objets actifs.  Les fonctions globales [AfxOleLockApp](../Topic/AfxOleLockApp.md) et [AfxOleUnlockApp](../Topic/AfxOleUnlockApp.md) mettent à jour le compte de l'application des objets actifs.  Si ce nombre est différent de zéro, l'application ne se termine pas lorsque l'utilisateur sélectionne Fermer dans le menu système ou Sortie dans le menu Fichier.  En revanche, la fenêtre principale de l'application est masquée \(mais pas détruite\) jusqu'à ce que toutes les demandes en attente des clients aient été terminées.  En général, `AfxOleLockApp` et `AfxOleUnlockApp` sont appelés des constructeurs et les destructeurs, respectivement, des classes qui supportent Automation.  
  
 Parfois des circonstances obligent le serveur de s'arrêter lorsqu'un client a toujours une référence à un objet.  Par exemple, une ressource dont le serveur dépend peut ne pas être disponible, ce qui cause une erreur du serveur.  L'utilisateur peut également fermer un document serveur qui contient les objets auxquels d'autres applications ont des références.  
  
 Dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)], consultez `IUnknown::AddRef` et `IUnknown::Release`.  
  
## Voir aussi  
 [Serveurs Automation](../mfc/automation-servers.md)   
 [AfxOleCanExitApp](../Topic/AfxOleCanExitApp.md)