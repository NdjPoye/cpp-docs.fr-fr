---
title: "Arri&#232;re-plan OLE&#160;: conteneurs et serveurs | Microsoft Docs"
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
  - "conteneurs, applications conteneur OLE"
  - "serveur complet"
  - "conteneurs OLE, applications conteneur"
  - "applications serveur complet OLE"
  - "applications serveur OLE, à propos des applications serveur"
  - "applications serveur OLE, applications mini-serveur"
  - "applications serveur"
  - "applications serveur, communication avec les conteneurs"
  - "applications serveur, définir"
  - "applications serveur, serveur complet et mini-serveur"
  - "applications serveur, spécification"
ms.assetid: dafbb31d-096c-4654-b774-12900d832919
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Arri&#232;re-plan OLE&#160;: conteneurs et serveurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une application conteneur est une application qui peut incorporer des éléments liés ou incorporés dans ses propres documents.  Les documents traités par une application conteneur doivent pouvoir stocker et afficher les composants de document OLE ainsi que les données créées par l'application elle\-même.  Une application doit également autoriser les utilisateurs à insérer de nouveaux éléments ou modifier des éléments existants en activant les applications de serveur si nécessaire.  Les spécifications d'interface utilisateur d'une application conteneur sont répertoriées dans l'article [Conteneurs : Problèmes d'interface utilisateur](../mfc/containers-user-interface-issues.md).  
  
 Une application serveur ou une application de composant est une application qui peut créer des composants de document OLE pour une utilisation par les applications conteneur.  Serveur d'applications supportent généralement le glisser\-déplacer ou la copie des données dans le presse\-papiers afin qu'une application conteneur puisse insérer les données comme incorporées ou liées.  Une application peut être à la fois un conteneur et un serveur.  
  
 La plupart des serveurs sont des applications autonomes ou des serveurs entiers ; ils peuvent être exécutés en tant qu'applications autonomes ou bien elles peuvent être lancés par une application conteneur.  Un miniserver est un type spécial d'application serveur qui peut être lancé uniquement par un conteneur.  Il ne peut pas être exécutée comme une application autonome.  Les serveurs Microsoft dessiner et Microsoft graphique sont des exemples de miniservers.  
  
 Les conteneurs et les serveurs ne communiquent pas directement.  Au lieu de cela, ils communiquent via les bibliothèques de liens dynamiques \(DLL\) du système OLE.  Ces DLL fournissent des fonctions que les conteneurs et les serveurs appellent, et les conteneurs et les serveurs fournissent les fonctions de rappel que les DLL appellent.  
  
 À l'aide de ces moyens de communication, un conteneur n'a pas besoin de connaître les détails d'implémentation de l'application serveur.  Elle permet à un conteneur de recevoir des éléments créés par n'importe quel serveur sans devoir définir les types de serveurs avec lequel ils peuvent être exécutés.  Par conséquent, l'utilisateur d'une application conteneur peut tirer des avantages des futures applications et formats de données.  Si ces applications sont des composants OLE, alors un document composite pourra ensuite incorporer les éléments créés par ces applications.  
  
## Voir aussi  
 [Arrière\-plan OLE](../mfc/ole-background.md)   
 [Arrière\-plan OLE : implémentation MFC](../mfc/ole-background-mfc-implementation.md)   
 [Conteneurs](../mfc/containers.md)   
 [Serveurs](../mfc/servers.md)   
 [Conteneurs : éléments clients](../mfc/containers-client-items.md)   
 [Serveurs : éléments du serveur](../mfc/servers-server-items.md)