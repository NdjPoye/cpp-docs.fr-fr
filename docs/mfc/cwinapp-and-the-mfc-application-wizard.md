---
title: "CWinApp et l&#39;Assistant Application MFC | Microsoft Docs"
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
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistants Application (C++), et CWinApp"
  - "CWinApp (classe), et Assistant Application MFC"
  - "MFC (C++), Assistants"
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinApp et l&#39;Assistant Application MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'elle crée une application squelette, l'Application MFC déclare une classe d'application dérivée de[CWinApp](../mfc/reference/cwinapp-class.md).  L'Application MFC crée également un fichier d'implémentation qui contient les éléments suivants :  
  
-   Une table des messages pour la classe d'application.  
  
-   Un constructeur vide de la classe.  
  
-   Une variable qui déclare un et un seul objet de la classe.  
  
-   Une implémentation standard de la fonction membre `InitInstance`.  
  
 La classe d'application est placée dans les fichiers sources d'en\-tête et de main du projet.  Les noms de la classe et des fichiers créés sont basés sur le nom du projet que vous fournissez dans l'Assistant d'Application MFC.  La méthode la plus facile pour consulter le code de ces classes est via [Affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
 Les implémentations et la table des messages standard fournies sont appropriées à de nombreuses fins, mais vous pouvez les modifier si nécessaire.  La plus intéressante de ces implémentations est la fonction membre `InitInstance`.  En général, vous allez ajouter du code à l'implémentation squelette de `InitInstance`.  
  
## Voir aussi  
 [CWinApp : classe d'application](../mfc/cwinapp-the-application-class.md)   
 [Fonctions membres CWinApp remplaçables](../mfc/overridable-cwinapp-member-functions.md)   
 [Services CWinApp spéciaux](../mfc/special-cwinapp-services.md)