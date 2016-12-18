---
title: "Comment&#160;: convertir un ruban MFC existant en ressource du ruban | Microsoft Docs"
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
  - "ruban MFC, convertir en ressource du ruban"
  - "ressource du ruban, convertir à partir d'un ruban MFC"
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: convertir un ruban MFC existant en ressource du ruban
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il est plus facile de visualiser, modifier, et conserver les ressources de ruban que les rubans codés manuellement.  Cette rubrique explique comment convertir un ruban manuellement encodé dans un projet MFC en une ressource ruban.  
  
 Vous devez avoir un projet MFC existant dont le code utilise les classes de ruban MFC, par exemple, [Classe CMFCRibbonBar](../mfc/reference/cmfcribbonbar-class.md).  
  
### Pour convertir un ruban MFC en ruban ressource  
  
1.  Dans Visual Studio, dans un projet MFC existant, ouvrez le fichier source dans lequel l'objet CMFCRibbonBar est initialisé.  En général, le fichier est mainfrm.cpp.  Ajoutez le code suivant après le code d'initialisation du ruban.  
  
    ```  
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");  
    ```  
  
     Enregistrez et fermez le fichier.  
  
2.  Générez et exécutez l'application MFC, puis dans le Bloc\-notes, ouvrez RibbonOutput.txt et copiez son contenu.  
  
3.  Dans Visual Studio, dans le menu **Projet**, cliquez sur **Ajouter une ressource**.  Dans la boîte de dialogue **Ajouter une nouvelle ressource**, sélectionnez **Ruban \(Concepteur visuel\)** puis cliquez sur **Nouveau**.  
  
     Visual Studio crée un ruban ressource et l'ouvre dans le concepteur.  L'ID de ressource de ruban est IDR\_RIBBON1, qui s'affiche dans **Affichage des ressources**.  Le ruban est défini dans le fichier XML de ribbon1.mfcribbon\-ms.  
  
4.  Dans Visual Studio, ouvrez ribbon1.mfcribbon\-ms, supprimez son contenu, puis collez le contenu de RibbonOutput.txt, que vous avez copié précédemment.  Enregistrez et fermez ribbon1.mfcribbon\-ms.  
  
5.  Ouvrez à nouveau le fichier source dans lequel l'objet de CMFCRibbonBar est initialisé \(en général, mainfrm.cpp\) et mettez en commentaire le code existant du ruban.  Ajoutez le code suivant après le code mis en commentaire.  
  
    ```  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);  
    ```  
  
6.  Générez le projet et exécutez l'application.  
  
## Voir aussi  
 [Concepteur de ruban \(MFC\)](../mfc/ribbon-designer-mfc.md)