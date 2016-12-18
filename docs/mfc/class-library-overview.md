---
title: "Vue d&#39;ensemble de la biblioth&#232;que de classes | Microsoft Docs"
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
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bibliothèques de classes"
  - "bibliothèques de classes, MFC"
  - "classes (C++), MFC"
  - "regrouper des classes MFC"
  - "MFC, bibliothèque de classes"
ms.assetid: 9b0e3152-ac39-4f52-91b4-f20aa3a674aa
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Vue d&#39;ensemble de la biblioth&#232;que de classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette présentation classe par catégorie et décrit les classes de la bibliothèque MFC \(Microsoft Foundation Class\) version 9.0.  Les classes MFC, une fois combinées, constituent une infrastructure d'application \(infrastructure d'une application écrite pour l'API Windows\).  Votre tâche de programmation est d'entrer le code spécifique à votre application.  
  
 Les classes de la bibliothèque sont présentées ici dans les catégories suivantes :  
  
-   [Classe racine : CObject](../mfc/root-class-cobject.md)  
  
-   [Classes d'architecture d'application MFC](../mfc/mfc-application-architecture-classes.md)  
  
    -   [Classes de prise en charge d'application et de thread](../mfc/application-and-thread-support-classes.md)  
  
    -   [Classes de routage de commandes](../mfc/command-routing-classes.md)  
  
    -   [Classes de document](../mfc/document-classes.md)  
  
    -   [Classes d'affichage \(architecture\)](../mfc/view-classes-architecture.md)  
  
    -   [Classes de fenêtre frame \(architecture\)](../mfc/frame-window-classes-architecture.md)  
  
    -   [Classes de modèle de document](../mfc/document-template-classes.md)  
  
-   [Fenêtre, boîte de dialogue et classes de contrôle](../mfc/window-dialog-and-control-classes.md)  
  
    -   [Classes de fenêtre frame \(Windows\)](../mfc/frame-window-classes-windows.md)  
  
    -   [Classes d'affichage \(Windows\)](../mfc/view-classes-windows.md)  
  
    -   [Classes de boîte de dialogue](../mfc/dialog-box-classes.md)  
  
    -   [Classes de contrôle](../mfc/control-classes.md)  
  
    -   [Classes de barres de contrôles](../mfc/control-bar-classes.md)  
  
-   [Classes de dessin et d'impression](../mfc/drawing-and-printing-classes.md)  
  
    -   [Classes de sortie \(contexte de périphérique\)](../mfc/output-device-context-classes.md)  
  
    -   [Classes d'outil de dessin](../mfc/drawing-tool-classes.md)  
  
-   [Classes simples de type de données](../mfc/simple-data-type-classes.md)  
  
-   [Classes Array, List et Map](../mfc/array-list-and-map-classes.md)  
  
    -   [Classes de modèle pour les tableaux, les listes et les mappages](../mfc/template-classes-for-arrays-lists-and-maps.md)  
  
    -   [Classes de tableau prêtes à l'emploi](../mfc/ready-to-use-array-classes.md)  
  
    -   [Classes de liste prêtes à l'emploi](../mfc/ready-to-use-list-classes.md)  
  
    -   [Classes de mappage prêtes à l'emploi](../mfc/ready-to-use-map-classes.md)  
  
-   [Classes des fichiers et des bases de données](../mfc/file-and-database-classes.md)  
  
    -   [Classes d'E\/S de fichier](../mfc/file-i-o-classes.md)  
  
    -   [Classes DAO](../mfc/dao-classes.md)  
  
    -   [Classes ODBC](../mfc/odbc-classes.md)  
  
    -   [Classes de base de données OLE](../mfc/ole-db-classes.md)  
  
-   [Classes liées à Internet et à la gestion réseau](../mfc/internet-and-networking-classes.md)  
  
    -   [Classes Windows Sockets](../mfc/windows-sockets-classes.md)  
  
    -   [Classes Internet win32](../mfc/win32-internet-classes.md)  
  
-   [Classes OLE](../mfc/ole-classes.md)  
  
    -   [Classes de conteneur OLE](../mfc/ole-container-classes.md)  
  
    -   [Classes serveur OLE](../mfc/ole-server-classes.md)  
  
    -   [Classes de transfert de données et de glisser\-déplacer OLE](../mfc/ole-drag-and-drop-and-data-transfer-classes.md)  
  
    -   [Classes de boîte de dialogue courantes OLE](../mfc/ole-common-dialog-classes.md)  
  
    -   [Classes d'automation OLE](../mfc/ole-automation-classes.md)  
  
    -   [Classes de contrôle OLE](../mfc/ole-control-classes.md)  
  
    -   [Classes de document actif](../mfc/active-document-classes.md)  
  
    -   [Classes liées à OLE](../mfc/ole-related-classes.md)  
  
-   [Classes d'exceptions et de débogage](../mfc/debugging-and-exception-classes.md)  
  
    -   [Classes de prise en charge du débogage](../mfc/debugging-support-classes.md)  
  
    -   [Classes d'exceptions](../mfc/exception-classes.md)  
  
 La section [Philosophie de la conception générale des classes](../mfc/general-class-design-philosophy.md) explique comment la bibliothèque MFC a été conçue.  
  
 Pour une vue d'ensemble de l'infrastructure, consultez [Utilisation des classes pour l'écriture d'applications Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  Certaines classes répertoriées ci\-dessus sont des classes à usage général, qui peuvent être utilisées en dehors de l'infrastructure et qui fournissent des abstractions utiles telles que des collections, des exceptions, des fichiers et des chaînes.  
  
 Pour afficher l'héritage d'une classe, utilisez le [Graphique de hiérarchie de classes](../mfc/hierarchy-chart.md).  
  
 Outre les classes répertoriées dans cette présentation, la bibliothèque MFC contient plusieurs fonctions globales, variables globales et macros.  Il existe une présentation générale et une liste détaillée de celles\-ci dans la rubrique [Macro MFC et Globals](../mfc/reference/mfc-macros-and-globals.md), qui suivent la référence alphabétique aux classes MFC.  
  
## Voir aussi  
 [MFC, applications de bureau](../mfc/mfc-desktop-applications.md)