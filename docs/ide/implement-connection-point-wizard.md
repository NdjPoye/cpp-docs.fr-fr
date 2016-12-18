---
title: "Assistant Impl&#233;mentation d&#39;un point de connexion | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.impl.cp.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Implémentation d'un point de connexion (Assistant C++)"
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assistant Impl&#233;mentation d&#39;un point de connexion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet Assistant implémente un point de connexion pour un objet COM.  Un objet connectable \(c'est\-à\-dire une source\) peut exposer un point de connexion pour son interface personnelle ou pour n'importe quelle interface sortante.  Visual C\+\+ et Windows proposent des bibliothèques de types possédant des interfaces sortantes.  Chaque interface sortante peut être implémentée par un client sur un objet \(c'est\-à\-dire un récepteur\).  
  
 Pour plus d'informations, consultez [Points de connexion ATL](../atl/atl-connection-points.md).  
  
 **Bibliothèques de types disponibles**  
 Affiche les bibliothèques de types disponibles contenant les définitions de l'interface pour laquelle vous pouvez implémenter des points de connexion.  Cliquez sur le bouton de sélection pour rechercher un fichier contenant la bibliothèque de types à utiliser.  
  
 **Emplacement**  
 Affiche l'emplacement de la bibliothèque de types actuellement sélectionnée dans la liste **Bibliothèques de types disponibles**.  
  
 **Interfaces**  
 Affiche les interfaces dont les définitions sont indiquées dans la bibliothèque de types actuellement sélectionnée dans la zone **Bibliothèques de types disponibles**.  
  
|Bouton de transfert|Description|  
|-------------------------|-----------------|  
|**\>**|Ajoute à la liste **Implémenter les points de connexion** le nom d'interface actuellement sélectionné dans la liste **Interfaces sources**.|  
|**\>\>**|Ajoute à la liste **Implémenter les points de connexion** le nom de toutes les interfaces disponibles dans la liste **Interfaces sources**.|  
|**\<**|Supprime le nom d'interface actuellement sélectionné dans la liste **Implémenter les points de connexion**.|  
|**\<\<**|Supprime les noms de toutes les interfaces actuellement affichées dans la liste **Implémenter les points de connexion**.|  
  
 **Implémenter les points de connexion**  
 Affiche le nom des interfaces pour lesquelles vous implémentez des points de connexion lorsque vous cliquez sur **Terminer**.  
  
## Voir aussi  
 [Implémentation d'un point de connexion](../ide/implementing-a-connection-point-visual-cpp.md)