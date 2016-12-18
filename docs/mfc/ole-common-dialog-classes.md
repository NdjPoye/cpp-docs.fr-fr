---
title: "Classes de bo&#238;tes de dialogue communes OLE | Microsoft Docs"
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
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes ActiveX (C++)"
  - "classes de boîtes de dialogue communes"
  - "classes de boîte de dialogue (C++), OLE"
  - "OLE (classes de boîtes de dialogue communes) (C++)"
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de bo&#238;tes de dialogue communes OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces tâches prennent en charge les tâches courantes OLE en implémentant un nombre de boîtes de dialogues OLE standards,  Elles fournissent également une interface utilisateur cohérente pour la fonctionnalité OLE.  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 Utilisé par l'infrastructure pour contenir des implémentations communes pour toutes les boîtes de dialogue OLE.  Toutes les classes de boîte de dialogue de la catégorie de l'interface utilisateur sont dérivées de la classe de base.  `COleDialog` ne peut pas être utilisé directemment.  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 Affiche la boîte de dialogue d'insertion, l'interface utilisateur standard pour insérer de nouveaux éléments liés ou incorporés à OLE.  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 Affiche la boîte de dialogue spéciale de collage, l'interface utilisateur standard pour implémenter la commande particulière de collage de modification.  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Affiche la boîte de dialogue de Liens de modification, l'interface utilisateur standard pour modifier les informations à propos les éléments liés.  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 Affiche la boîte de dialogue de l'icône de modification, l'interface utilisateur standard pour modifier l'icône associée à des éléments liés ou incorporés à OLE.  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 Affiche la boîte de dialogue de conversion, l'interface utilisateur standard pour convertir des éléments OLE d'un type à un autre.  
  
 [COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)  
 Encapsule la boîte de dialogue des propriétés commune OLE de Windows.  Les boîtes de dialogues Propriétés OLE communes fournissent un moyen facile d'afficher et de modifier les propriétés d'un élément OLE de document d'une manière compatible avec les normes windows.  
  
 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)  
 Affiche la boîte de dialogue mise à jour, l'interface utilisateur standard pour mettre à jour tous les liens dans un document.  La boîte de dialogue contient un indicateur de progression pour indiquer l'achèvement du processus de mise à jour.  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 Affiche la boîte de dialogue source de modification, l'interface utilisateur standard pour modifier la source ou la source du lien.  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 Affiche les boîtes de dialogue Serveur Occupé et Serveur ne Répond Pas, l'interface utilisateur standard pour gérer des appels aux applications actives.  Affiché généralement automatiquement par l'implémentation de `COleMessageFilter`  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)