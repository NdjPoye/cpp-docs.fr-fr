---
title: "Cr&#233;ation d&#39;une application MFC de style Explorateur de fichiers | Microsoft Docs"
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
  - "vc.appwiz.mfcexplorer.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "navigateurs, applications de style Explorateur"
  - "applications de style Explorateur, créer"
  - "applications MFC, de type Explorateur Windows"
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;une application MFC de style Explorateur de fichiers
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

De nombreuses applications système Windows utilisent l'interface utilisateur de l'Explorateur de Fichiers  Par exemple, lorsque vous démarrez l'Explorateur de Fichiers, vous voyez une application comportant une barre de fractionnement verticale séparant la zone cliente.  La partie gauche de la zone cliente fournit les fonctionnalités de navigation et d'exploration, tandis que sa partie droite affiche des détails relatifs à la sélection effectuée dans la partie gauche.  Lorsqu'un utilisateur clique sur un élément dans le volet de gauche, l'application remplit de nouveau le volet de droite.  Dans une application MDI, vous pouvez utiliser les commandes du menu **Affichage** pour modifier la quantité de détails affichée dans le volet de droite. \(en revanche, dans une application dotée d'une interface SDI ou prenant en charge plusieurs documents de niveau supérieur, vous ne pouvez modifier la quantité de détails qu'à l'aide des boutons de barre d'outils\).  
  
 Le contenu des volets dépend de l'application.  Dans un navigateur utilisant le système de fichiers, le volet de gauche présente une vue hiérarchique des répertoires, des ordinateurs ou des groupes d'ordinateurs, tandis que le volet de droite affiche les dossiers, les fichiers individuels ou les ordinateurs, ainsi que les détails s'y rapportant.  Le contenu ne doit pas nécessairement correspondre à des fichiers.  Il peut s'agir de messages électroniques, de relevés d'erreur ou d'autres éléments contenus dans une base de données.  
  
 L'Assistant se charge de créer les classes suivantes :  
  
-   La classe **CLeftView** définit le volet de gauche de la zone cliente.  Elle est toujours dérivée de [CTreeView](../../mfc/reference/ctreeview-class.md).  
  
-   La classe C*ProjName*View définit le volet de droite de la zone cliente.  Par défaut, elle est dérivée de [CListView](../../mfc/reference/clistview-class.md), mais il peut s'agir d'un autre type de vue, selon la classe que vous spécifiez dans la liste **Classe de base** située dans la page [Classes générées](../../mfc/reference/generated-classes-mfc-application-wizard.md) de l'Assistant.  
  
 L'application générée peut être dotée d'une architecture à interface monodocument \(SDI\), multidocument \(MDI\), ou encore une architecture prenant en charge plusieurs documents de niveau supérieur.  Chaque fenêtre frame que l'application crée est fractionnée dans le sens vertical à l'aide de [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md).  Le codage de ce type d'application est semblable au codage d'une application MFC normale utilisant un séparateur, excepté que ce type d'application dispose de vues de contrôle distinctes dans chacun des volets fractionnés.  
  
 Si vous utilisez la vue liste par défaut dans le volet de droite, l'Assistant crée des choix de menu \(dans les applications dotées d'une interface MDI uniquement\) et des boutons de barre d'outils supplémentaires pour permettre de basculer le style de vue entre les modes de grandes icônes, de petites icônes, de liste et de détails.  
  
### Pour commencer à créer un exécutable MFC de style Explorateur de Fichiers  
  
1.  Suivez les instructions indiquées dans [Création d'une application MFC](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  Dans la page [Type d'application](../../mfc/reference/application-type-mfc-application-wizard.md) de l'Assistant Application MFC, sélectionnez le style de projet **Explorateur de Fichiers**.  
  
3.  Définissez les autres options voulues dans les autres pages de l'Assistant.  
  
4.  Cliquez sur **Terminer** pour générer l'application squelette.  
  
 Pour plus d'informations, consultez :  
  
-   [Types multidocuments, vues et fenêtres frame](../../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Classes vues dérivées](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Choix en matière de conception d'applications](../../mfc/application-design-choices.md)  
  
## Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)   
 [Création d'une application MFC de style navigateur Web](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)   
 [Création d'une application MFC basée sur les formulaires](../../mfc/reference/creating-a-forms-based-mfc-application.md)