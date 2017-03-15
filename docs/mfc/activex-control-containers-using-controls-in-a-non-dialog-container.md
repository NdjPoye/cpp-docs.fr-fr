---
title: "Conteneurs de contr&#244;les ActiveX&#160;: utilisation de contr&#244;les dans un conteneur autre que de bo&#238;te de dialogue | Microsoft Docs"
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
  - "conteneurs de contrôles ActiveX (C++), insérer des contrôles"
  - "conteneurs de contrôles ActiveX (C++), conteneurs autres que de boîte de dialogue"
  - "contrôles ActiveX (C++), créer"
  - "Create (méthode) (C++), contrôles ActiveX"
  - "CreateControl (méthode)"
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Conteneurs de contr&#244;les ActiveX&#160;: utilisation de contr&#244;les dans un conteneur autre que de bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans certaines applications, telles qu'une application SDI ou MDI, vous souhaiterez inclure un contrôle dans une fenêtre de l'application.  La méthode **Create** de la classe encapsulatrice, insérée par Visual C\+\+, peut créer une instance de contrôle dynamiquement, sans avoir besoin de la boîte de dialogue.  
  
 La méthode **Create** présente les paramètres suivants :  
  
 `lpszWindowName`  
 Pointeur vers le texte à afficher dans le texte ou la propriété de légende du contrôle \(le cas échéant\).  
  
 `dwStyle`  
 Styles de fenêtres  Pour une liste plus complète, consultez [CWnd::CreateControl](../Topic/CWnd::CreateControl.md).  
  
 `rect`  
 Spécifie la taille et l'emplacement du contrôle.  
  
 `pParentWnd`  
 Spécifie la fenêtre parente du contrôle, généralement `CDialog`.  Ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l'ID du contrôle et peut être utilisé par le conteneur pour désigner le contrôle.  
  
 Un exemple d'utilisation de cette fonction pour créer dynamiquement un contrôle ActiveX serait en mode formulaire d'une application SDI.  Vous pouvez créer ensuite une instance de contrôle dans le gestionnaire `WM_CREATE` de l'application.  
  
 Pour cet exemple, `CMyView` est la classe d'affichage principale, `CCirc` est la classe encapsulatrice, et CIRC.H est le fichier d'en\-tête \(. H\) fichier de la classe encapsulatrice.  
  
 Implémenter cette fonctionnalité est un processus en quatre phases.  
  
### Pour créer dynamiquement un contrôle ActiveX dans une fenêtre non dialogue  
  
1.  Insérez CIRC.H dans CMYVIEW.H, juste avant la définition de classe `CMyView`:  
  
     [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/CPP/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]  
  
2.  Ajoutez un attribut \(type `CCirc`\) à la section protégée par la définition de classe `CMyView` trouvée dans CMYVIEW.H :  
  
     [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/CPP/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]  
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/CPP/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]  
  
3.  Ajoutez un gestionnaire de messages `WM_CREATE` à la classe `CMyView`.  
  
4.  Dans la fonction gestionnaire, `CMyView::OnCreate`, effectuez un appel à la fonction `Create` du contrôle à l'aide du pointeur **this** dans une fenêtre parente :  
  
     [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/CPP/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]  
  
5.  Régénérez le projet.  Un contrôle de Circ sera créé dynamiquement chaque fois que la vue de l'application est créée.  
  
## Voir aussi  
 [Conteneurs de contrôles ActiveX](../mfc/activex-control-containers.md)