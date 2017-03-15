---
title: "Presse-papiers&#160;: utilisation du Presse-papiers Windows | Microsoft Docs"
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
  - "Presse-papiers (C++), commandes"
  - "Presse-papiers (C++), Presse-papiers Windows (API)"
  - "commandes du Presse-papiers"
  - "commandes du Presse-papiers, implémenter"
  - "commandes (C++), implémenter l'édition"
  - "Fonctions du gestionnaire de commandes Couper/Copier et Coller"
  - "fonctions gestionnaires, commandes Couper/Copier et Coller"
  - "Presse-papiers Windows (C++)"
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Presse-papiers&#160;: utilisation du Presse-papiers Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment utiliser l'API standard du Presse\-papiers Windows dans votre application de MFC.  
  
 La plupart des applications Windows prennent en charge la coupe ou la copie de données dans le Presse\-papiers Windows et le collage de données du Presse\-papiers.  Les formats de données du Presse\-papiers varient entre les applications.  L'infrastructure prend en charge qu'un nombre limité de formats de Presse\-papiers pour un nombre limité de classes.  Vous implémenterez normalement les commandes liées au Presse\-papiers — Couper, Copier et Coller — dans le menu Edition pour votre vue.  La bibliothèque de classes définit les ID de commande pour les commandes : **ID\_EDIT\_CUT**, **ID\_EDIT\_COPY** et **ID\_EDIT\_PASTE**.  Leurs invites en ligne de message sont également définies.  
  
 [Messages et Commandes dans l'Infrastructure](../mfc/messages-and-commands-in-the-framework.md) explique comment gérer les commandes du menu dans votre application en mappant la commande de menu à la fonction gestionnaire.  Tant que votre application ne définit pas de fonctions gestionnaires pour les commandes du Presse\-papiers dans le menu Edition, elles restent désactivées.  Pour écrire des fonctions gestionnaires pour les commandes Couper et Copier, implémentez sélection dans votre application.  Pour écrire une fonction gestionnaire de la commande Coller, interrogez le Presse\-papiers pour savoir s'il contient des données dans un format que votre application peut accepter.  Par exemple, pour activer la commande Copier, vous pouvez entrer dans un gestionnaire quelque chose similaire à ce qui suit :  
  
 [!code-cpp[NVC_MFCListView#2](../mfc/codesnippet/CPP/clipboard-using-the-windows-clipboard_1.cpp)]  
  
 Les commandes Couper, Copier et Coller n'ont de sens que dans certains contextes.  Les commandes Couper et Copier doivent être activées uniquement lorsque quelque chose est sélectionné, et la commande Coller uniquement lorsque quelque chose se trouve dans le Presse\-papiers.  Vous pouvez spécifier ce comportement en définissant des fonctionnalités du gestionnaire de mises à jour qui activent ou désactivent ces commandes selon le contexte.  Pour plus d'informations, consultez [Procédure de mise à jour d'objets de l'interface utilisateur](../mfc/how-to-update-user-interface-objects.md).  
  
 La bibliothèque de MFC fournit la prise en charge du Presse\-papiers de pour l'édition de texte avec les classes d' `CEdit` et d' `CEditView` .  Les classes d'OLE simplifient également l'implémentation d'opérations du presse\-papiers impliquant des éléments d'OLE.  Pour plus d'informations sur les classes d'OLE, consultez [Presse\-papiers : utilisation du mécanisme OLE du Presse\-papiers](../mfc/clipboard-using-the-ole-clipboard-mechanism.md).  
  
 L'implémentation d'autres commandes du menu Edition, telles que Défaire \(**ID\_EDIT\_UNDO**\) et Refaire \(**ID\_EDIT\_REDO**\), est également laissée à vous.  Si votre application ne prend pas en charge ces commandes, vous pouvez facilement les supprimer à partir de votre fichier de ressources à l'aide des éditeurs de ressources Visual C\+\+.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Copier et coller des données](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [À l'aide du mécanisme OLE du presse\-papiers](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
## Voir aussi  
 [Presse\-papiers](../mfc/clipboard.md)