---
title: "Cr&#233;ation d&#39;une application conteneur de documents actifs | Microsoft Docs"
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
  - "documents actifs (conteneurs) (C++), créer"
  - "documents actifs (C++), conteneurs"
  - "applications (MFC), documents actifs (conteneurs)"
  - "conteneurs (C++), document actif"
  - "MFC COM (C++), documents actifs (contenance)"
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;une application conteneur de documents actifs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le moyen plus simple et le plus recommandé pour créer une application de conteneur de documents actifs consiste à créer une application conteneur de MFC EXE graĉe à l'assistant d'Application MFC, puis modifier l'application pour prendre en charge la relation contenant\-contenu de document actif.  
  
#### Création d'une application conteneur de documents actifs  
  
1.  Dans le menu **Fichier**, cliquez sur **Projet** dans le sous\-menu **Nouveau**.  
  
2.  Dans le volet gauche, cliquez sur le type de projet **Visual C\+\+**.  
  
3.  Sélectionnez **Application MFC** dans le volet droit.  
  
4.  Nom du projet `MyProj`, cliquez sur **OK**.  
  
5.  Sélectionnez la page **Prise en charge doc. composés**.  
  
6.  Sélectionnez l'option **Conteneur** ou **Conteneur\/serveur entier**.  
  
7.  Activez la case à cocher **Conteneur de documents actifs**.  
  
8.  Cliquez sur **Terminer**.  
  
9. Lorsque l'Application MFC termine de générer l'application, ouvrez les fichiers suivants à l'aide de l'explorateur de solutions :  
  
    -   MyProjview.cpp  
  
10. Dans MyProjview.cpp, apportez les modifications suivantes :  
  
    -   Dans `CMyProjView::OnPreparePrinting`, remplacez le contenu de la fonction par le code suivant :  
  
         [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/CPP/creating-an-active-document-container-application_1.cpp)]  
  
     `OnPreparePrinting` fournit la prise en charge de l'impression.  Ce code remplace `DoPreparePrinting`, qui est la préparation d'impression par défaut.  
  
     La relation contenant\-contenu de document actif est un modèle amélioré d'impression :  
  
    -   Vous pouvez appeler au préalable le document actif via son interface `IPrint` et lui indiquer de s'imprimer.  Ceci est différent de la relation contenant\-contenu précédente de OLE, dans laquelle le conteneur defait afficher une image de l'élément contenu dans l'objet imprimant `CDC`.  
  
    -   Si cette tentative échoue, indiquez à l'élément contenu de s'imprimer via son interfaced'`IOleCommandTarget`  
  
    -   Si cette tentative échoue, faites votre propre rendu de l'élément.  
  
     Les fonctions membre statiques `COleDocObjectItem::OnPrint` et `COleDocObjectItem::OnPreparePrinting`, implémentées dans le code précédent, gérent ce schéma amélioré d'impression.  
  
11. Ajoutez toute implémentation que vous ayez pu faire et générez l'application.  
  
## Voir aussi  
 [Relation contenant\-contenu de document actif](../mfc/active-document-containment.md)