---
title: "Impl&#233;mentation d&#39;espaces de travail dans des contr&#244;les de liste | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "contrôles de liste, espaces de travail"
  - "espaces de travail dans un contrôle de liste"
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Impl&#233;mentation d&#39;espaces de travail dans des contr&#244;les de liste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par défaut, un contrôle de liste réorganise tous les éléments sous forme de grille standard.  Toutefois, une autre méthode est prise en charge, les emplacements de travail, qui organise les éléments de liste en groupes rectangulaires.  Pour une image d'un contrôle de liste qui implémente les emplacements de travail, consultez sur l'utilisation des contrôles list VIEW dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Les emplacements de travail sont visibles uniquement lorsque le contrôle de liste est en mode icônes ou de petites icônes.  Toutefois, les emplacements de travail actifs sont maintenus si la vue est basculée en mode de rapport ou de liste.  
  
 Les emplacements de travail peuvent être utilisés pour afficher une bordure vide \(à gauche, au dessus et\/ou à droite des éléments\), ou provoquer l'affichage d'une barre de défilement horizontale lorsqu'il n'y aurait normalement pas.  Une autre utilisation courante consiste à créer plusieurs emplacements de travail vers lesquels les éléments peuvent être déplacés ou supprimés.  Avec cette méthode, vous pouvez créer des domaines dans une vue avec différentes significations.  L'utilisateur peut ensuite demander les éléments par catégorie en les plaçant dans une zone différente.  Un exemple de cette approche est une vue d'un système de fichiers qui possède une zone pour les fichiers en lecture\-écriture et une zone différente pour les fichiers en lecture seule.  Si un élément de fichier était entré dans la zone en lecture seule, il deviendrait automatiquement en lecture seule.  Déplacer un fichier de la zone en lecture seule dans la zone en lecture\/écriture entraînera la lecture\/écriture du fichier.  
  
 `CListCtrl` fournit plusieurs fonctions membres pour créer et gérer des postes de travail dans votre contrôle de liste.  [GetWorkAreas](../Topic/CListCtrl::GetWorkAreas.md) et [SetWorkAreas](../Topic/CListCtrl::SetWorkAreas.md) extraient et définissent un tableau d'objets `CRect` \(ou de structures `RECT` \), qui stockent les emplacements de travail actuellement implémentés pour le contrôle de liste.  En outre, [GetNumberOfWorkAreas](../Topic/CListCtrl::GetNumberOfWorkAreas.md) récupère le nombre actuel d'emplacements pour votre contrôle de liste \(par défaut, zéro\).  
  
## Éléments et emplacements de travail  
 Lorsqu'un emplacement de travail est créé, les éléments qui se trouvent dans l'emplacement de travail en deviennent membres.  De même, si un élément est déplacé dans un emplacement de travail, il devient membre de l'emplacement de travail dans lequel il a été déplacé.  Si un élément ne se trouve dans la plage d'aucun emplacement de travail, il devient automatiquement un membre de l'emplacement de travail du premier index \(0\) .  Si vous souhaitez créer un élément et le faire placer dans un emplacement de travail spécifique, vous devez créer l'élément et l'entrer dans l'emplacement de travail voulu par un appel à [SetItemPosition](../Topic/CListCtrl::SetItemPosition.md).  Le deuxième exemple suivant montre cette technique.  
  
 L'exemple suivant implémente les emplacements de travail \(`rcWorkAreas`\), de taille égale avec une bordure de 10 pixels autour de chaque emplacement de travail, dans un contrôle de liste\(`m_WorkAreaListCtrl`\).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/CPP/implementing-working-areas-in-list-controls_1.cpp)]  
  
 L'appel à [ApproximateViewRect](../Topic/CListCtrl::ApproximateViewRect.md) a été effectuée pour obtenir une estimation de la surface totale requise pour consulter tous les éléments dans une zone.  Cette évaluation est alors divisée en quatre régions et terminée avec une bordure niveau 5 d'un minimum.  
  
 L'exemple suivant affecte les éléments de liste existants à chaque groupe \(`rcWorkAreas`\) et actualise l'affichage de contrôle \(`m_` `WorkAreaListCtrl`\) pour terminer le résultat.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/CPP/implementing-working-areas-in-list-controls_2.cpp)]  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)