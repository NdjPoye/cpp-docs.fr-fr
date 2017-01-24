---
title: "TN020&#160;: conventions de d&#233;nomination d&#39;ID et de num&#233;rotation | Microsoft Docs"
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
  - "vc.id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "identificateurs de ressources"
  - "identificateurs de ressources, dénomination et numérotation"
  - "TN020"
ms.assetid: aecbd2cf-68b3-47f6-ae21-b1f507917245
caps.latest.revision: 17
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN020&#160;: conventions de d&#233;nomination d&#39;ID et de num&#233;rotation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit les conventions de désignation et de numérotation de l'ID que MFC 2,0 utilise pour les ressources, commandes, chaînes, contrôles, et fenêtres enfants.  
  
 Les conventions de désignation et de numérotation de l'ID MFC sont conçues pour répondre aux exigences suivantes :  
  
-   Fournir une norme de désignation d'ID cohérente utilisée au delà de la bibliothèque MFC et des applications MFC prises en charge par l'éditeur de ressources Visual C\+\+.  Cela simplifie la vie du programmeur pour l'interprétation du type et de l'origine d'une ressource de son ID.  
  
-   Accentuer la relation forte 1 à 1 entre certains types d'ID.  
  
-   Se conformer aux normes déjà largement utilisées pour désigner des ID dans Windows.  
  
-   Partitionner l'espace de numérotation d'ID.  Les numéros d'ID peuvent être assignés par le programmeur, MFC, Windows, et par les ressources éditées par Visual C\+\+.  Un partitionnement approprié permettra d'éviter la duplication des numéros d'ID.  
  
## La convention de désignation des préfixes d'ID  
 Plusieurs types d'ID peuvent se produire dans une application.  La convention de désignation d'ID MFC définit différents préfixes pour différents types de ressource.  
  
 MFC utilise le préfixe « IDR\_ » pour indiquer un ID de ressource qui s'applique à plusieurs types de ressource.  Par exemple, pour une fenêtre frame donnée, MFC utilise le même préfixe « IDR\_ » pour indiquer un menu, un accélérateur, une chaîne et une ressource icône.  Le tableau suivant indique les différents préfixes et leur utilisation :  
  
|Préfixe|Utilisez|  
|-------------|--------------|  
|IDR\_|Pour plusieurs types de ressource \(principalement utilisés pour les menus, les accélérateurs, et les rubans\).|  
|IDD\_|Pour les ressources modèles de boîte de dialogue \(par exemple, IDD\_DIALOG1\).|  
|IDC\_|Pour les ressources curseur.|  
|IDI\_|Pour les ressources icône.|  
|.IDB\_|Pour les ressources bitmap.|  
|IDS\_|Pour les ressources chaîne.|  
  
 A l'intérieur d'une ressource boite de dialogue, MFC suit ces conventions :  
  
|Préfixe ou étiquette|Utilisez|  
|--------------------------|--------------|  
|IDOK, IDCANCEL|Pour les ID standard de bouton poussoir.|  
|IDC\_|Pour d'autres contrôles de boîte de dialogue.|  
  
 Le préfixe « IDC\_ » est également utilisée pour les curseurs.  Ce conflit dans la désignation n'est généralement pas un problème car une application standard possède peu de curseurs et de nombreux contrôles de boîte de dialogue.  
  
 A l'intérieur d'une ressource menu, MFC suit ces conventions :  
  
|Préfixe|Utilisez|  
|-------------|--------------|  
|IDM\_|Pour les éléments de menu qui n'utilisent pas l'architecture de commande MFC.|  
|ID\_|Pour les commandes de menu qui utilisent l'architecture de commande MFC.|  
  
 Les commandes qui suivent l'architecture de commande MFC doivent avoir un gestionnaire de commandes `ON_COMMAND` et peuvent avoir un gestionnaire `ON_UPDATE_COMMAND_UI`.  Si ces gestionnaires de commandes suivent l'architecture de commande MFC, ils fonctionneront correctement qu'ils soient liés à une commande de menu, un bouton de barre d'outils, ou un bouton de barre de boîte de dialogue.  Le même préfixe « ID\_ » est également utilisé pour une chaîne d'invite de menu qui s'affiche dans la barre des messages du programme.  La plupart des éléments de menu dans votre application doivent respecter les conventions de commande MFC.  Tous les ID de commande standard \(par exemple, `ID_FILE_NEW`\) suivent cette convention.  
  
 MFC utilise également « IDP\_ » comme une forme particulière de chaînes \(au lieu de « IDS\_ »\).  Les chaînes avec le préfixe « IDP\_ » sont des invites, c'est à dire, des chaînes utilisées dans des boites de messages. Les chaînes « IDP\_ » peuvent contenir "%1" et "%2 " comme espaces réservés de chaînes déterminées par le programme. Les chaînes « IDP\_ » ont généralement des rubriques d'aide associées, et les chaînes « IDS\_ » non. Les chaînes « IDP\_ » sont toujours localisées, et les chaînes « IDS\_ » peuvent ne pas l'être.  
  
 La bibliothèque MFC utilise également le préfixe « IDW\_ » comme une forme particulière d'ID de contrôle \(au lieu de « IDC\_ »\).  Ces ID sont assignés aux fenêtres enfants telles que les vues et les séparateurs des classes d'infrastructure.  Les ID d'implémentation MFC sont précédés par « AFX\_ ».  
  
## La convention de numérotation d'ID  
 Le tableau suivant répertorie les plages valides pour les ID des types spécifiques.  Certaines des limites sont des limites techniques d'implémentation, et d'autres sont des conventions conçues pour empêcher vos ID de se heurter à des ID prédéfinis par Windows ou à des implémentations par défaut de MFC.  
  
 Nous vous recommandons vivement de définir tous les ID dans des plages recommandées.  La limite inférieure de ces plages est 1 car 0 n'est pas utilisé.  Nous vous recommandons d'utiliser la convention courante et d'utiliser 100 ou 101 comme premier ID.  
  
|Préfixe|Type de ressource|Plage valide|  
|-------------|-----------------------|------------------|  
|IDR\_|plusieurs|1 à 0x6FFF|  
|IDD\_|modèles de boîte de dialogue|1 à 0x6FFF|  
|IDC\_,IDI\_,IDB\_|curseurs, icônes, bitmaps|1 à 0x6FFF|  
|IDS\_, IDP\_|chaînes générales|1 à 0x7FFF|  
|ID\_|commandes|0x8000 à 0xDFFF|  
|IDC\_|contrôles|8 à 0xDFFF|  
  
 Les raisons pour ces bornes limites :  
  
-   Par convention, la valeur d'ID 0 n'est pas utilisée.  
  
-   Les limitations d'implémentation Windows restreignent les véritables ID de ressource pour être inférieurs ou égaux à 0x7FFF.  
  
-   L'infrastructure interne de MFC réserve ces plages :  
  
    -   0x7000 à 0x7FFF \(voir afxres.h\)  
  
    -   0xE000 à 0xEFFF \(voir afxres.h\)  
  
    -   16000 à 18000 \(voir afxribbonres.h\)  
  
     Ces plages peuvent changer dans les prochaines implémentations de MFC.  
  
-   Plusieurs commandes de système Windows utilisent la plage de 0xF000 à 0xFFFF.  
  
-   Les ID de contrôle de 1 à 7 sont réservés pour les contrôles standard tels qu'IDOK et IDCANCEL.  
  
-   La plage de 0x8000 à 0xFFFF pour les chaînes est réservée aux invites de menu pour les commandes.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)