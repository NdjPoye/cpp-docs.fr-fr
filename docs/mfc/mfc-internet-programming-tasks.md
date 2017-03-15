---
title: "T&#226;ches de programmation Internet MFC | Microsoft Docs"
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
  - "applications Internet, premières étapes"
  - "applications Internet, mise en route"
ms.assetid: 6377e9b8-07c4-4380-b63b-05f5a9061313
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# T&#226;ches de programmation Internet MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette section contient des procédures détaillées pour ajouter la prise en charge d'Internet dans vos applications.  Les rubriques suivantes expliquent comment utiliser les classes de MFC internet pour vérifier vos applications existantes, et comment ajouter la prise en charge des documents actifs vers votre composant COM existant.  Voulez\-vous créer un document avec des scores de cotations boursières à la minute, des scores de football de Pittsburgh, et la dernière température en Antarctique ?  Microsoft fournit plusieurs technologies pour vous aider à le faire sur Internet.  
  
 Les technologies actives incluent des contrôles ActiveX \(anciennement contrôles OLE\) et des documents actifs ; WinInet pour récupérer facilement et en stockant les fichiers sur Internet ; et monikers asynchrones à télécharger efficace de données.  Visual C\+\+ propose des assistants pour vous feront découvrir une application de démarreur.  Pour une présentation de ces technologies, consultez [Notions de programmation Internet de MFC](../mfc/mfc-internet-programming-basics.md) et l'[MFC COM](../mfc/mfc-com.md).  
  
 Vous avez toujours souhaité stocker sur le serveur un fichier mais n'avez pas appris les protocoles de Winsock et la programmation réseau ?  Les classes de WinInet encapsulent ces protocoles, vous fournissant un jeu unique de fonctions qui vous permettent d'écrire une application cliente sur Internet pour télécharger des fichiers à l'aide de le protocole HTTP, FTP, et Gopher.  Vous pouvez utiliser WinInet pour rechercher des répertoires sur votre disque dur ou dans le monde.  Vous pouvez de façon transparente collecter des données de différents types, et le entrez dans une interface intégrée.  
  
 Avez\-vous de grandes quantités de données à télécharger ?  Des monikers asynchrones fournit une solution de modèle COM \(component object model\) pour le rendu progressif d'objets.  WinInet peut également être utilisé de manière asynchrone.  
  
 Le tableau suivant décrit quelques une des opérations réalisables avec ces technologies.  
  
|Vous avez|Vous souhaitez|Vous devez|  
|---------------|--------------------|----------------|  
|Serveur Web.|Connexions et informations de suivi sur les demandes d'URL.|Entrez un filtre, les notifications de requête pour les événements d'ouverture de session et le mappage d'URL.|  
|Navigateur Web.|Fournissez le contenu dynamique.|Créez les contrôles et les documents actifs ActiveX.|  
|Une application document\-basée.|Ajouter la prise en charge au serveur un fichier.|Utilisez WinInet ou monikers asynchrones.|  
  
 Consultez les rubriques suivantes pour obtenir des détails pour vous lancer :  
  
-   [Choix en matière de conception d'applications](../mfc/application-design-choices.md)  
  
-   [Écriture d'applications MFC](../mfc/writing-mfc-applications.md)  
  
-   [Contrôles ActiveX sur Internet](../mfc/activex-controls-on-the-internet.md)  
  
-   [Mise à niveau d'un contrôle ActiveX](../mfc/upgrading-an-existing-activex-control.md)  
  
-   [Documents actifs sur Internet](../mfc/active-documents-on-the-internet.md)  
  
-   [Monikers asynchrones sur Internet](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Test des applications Internet](../mfc/testing-internet-applications.md)  
  
-   [Sécurité Internet](../mfc/internet-security-cpp.md)  
  
## Voir aussi  
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)   
 [Informations Internet par tâche](../mfc/internet-information-by-task.md)