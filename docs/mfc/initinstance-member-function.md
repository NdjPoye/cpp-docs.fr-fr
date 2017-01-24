---
title: "InitInstance, fonction membre | Microsoft Docs"
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
  - "InitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications (MFC), initialiser"
  - "initialiser des applications MFC"
  - "InitInstance (méthode)"
  - "MFC (C++), initialiser"
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InitInstance, fonction membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le système d'exploitation Windows vous permet d'exécuter plus d'une copie, ou « instance, » de la même application.  `WinMain` appelle [InitInstance](../Topic/CWinApp::InitInstance.md) chaque fois qu'une nouvelle instance d'application démarre.  
  
 L'implémentation standard de `InitInstance` créée par l'Assistant Application MFC effectue les tâches suivantes :  
  
-   Comme action centrale, crée des modèles de document qui créent ensuite des documents, des vues, et des cadres.  Pour une description de ce processus, consultez [Création d'un modèle de document](../mfc/document-template-creation.md).  
  
-   Charge les options de fichier standard d'un fichier .ini ou du Registre windows, notamment les noms des fichiers récemment utilisés.  
  
-   Enregistre un ou plusieurs modèles de document.  
  
-   Pour une application MDI, crée une fenêtre cadre principale.  
  
-   Traite la ligne de commande pour ouvrir un document spécifié sur la ligne de commande ou ouvrir un nouveau document vide.  
  
 Vous pouvez ajouter votre propre code d'initialisation ou modifier le code écrit par l'Assistant.  
  
> [!NOTE]
>  Les applications MFC doivent être initialisées comme un cloisonnement à thread unique \(STA\).  Si vous appelez [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) dans la substitution de `InitInstance`, spécifiez `COINIT_APARTMENTTHREADED` \(et non `COINIT_MULTITHREADED`\).  Pour plus d'informations, consultez PRB : L'application MFC cesse de répondre quand vous démarrez l'application comme un cloisonnement multithread \(828643\) à [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;828643](http://support.microsoft.com/default.aspx?scid=kb;en-us;828643).  
  
## Voir aussi  
 [CWinApp : classe d'application](../mfc/cwinapp-the-application-class.md)