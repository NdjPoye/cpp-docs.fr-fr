---
title: "Gestion des donn&#233;es d&#39;&#233;tat des modules MFC | Microsoft Docs"
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
  - "gestion des données (C++)"
  - "gestion des données (C++), modules MFC"
  - "interfaces exportées et état global (C++)"
  - "état global (C++)"
  - "MFC (C++), gérer des données d'état"
  - "état du module restauré"
  - "états des modules, enregistrer et restaurer"
  - "modules multiples"
  - "procédure de fenêtre (points d'entrée) (C++)"
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion des donn&#233;es d&#39;&#233;tat des modules MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les données d'état des modules de MFC et comment cet état est mis à jour lorsque le flux d'exécution \(il faut du code de chemin d'accès via une application lors de l'exécution\) entre et laisse un module.  L'échange des états de modules avec les macros `AFX_MANAGE_STATE` et `METHOD_PROLOGUE` est également présenté.  
  
> [!NOTE]
>  Le terme « module » fait référence à un programme exécutable, ou à une DLL \(ou un ensemble de DLL\) qui s'exécutent indépendamment du reste de l'application, mais utilise une copie partagée de la DLL MFC.  Un contrôle ActiveX est un exemple classique de module.  
  
 Comme illustré ci\-dessous, MFC contient des données d'état pour chaque module utilisé dans une application.  Des exemples de ces données sont les handles d'instance Windows \(utilisées pour charger des ressources\), les pointeurs vers les objets actuels d'une application `CWinApp` et `CWinThread`, les nombres de références de module OLE, et plusieurs maps qui maintiennent les connexions entre les handles d'objet Windows et les instances correspondantes d'objets MFC.  Toutefois, lorsqu'une application utilise plusieurs modules, les données d'état de chaque module ne sont pas pour toute l'application.  En revanche, chaque module possède sa propre copie privée des données d'état de MFC.  
  
 ![Données d'état d'un module unique &#40;application&#41;](../mfc/media/vc387n1.png "vc387N1")  
Données d'état d'un module unique \(application\)  
  
 Les données d'état d'un module sont contenus dans une structure et sont toujours disponibles via un pointeur à cette structure.  Lorsque le flux d'exécution entre dans un module particulier, comme le montre l'illustration suivante, l'état du module doit être "actuel" ou "effectif".  Par conséquent, chaque objet thread a un pointeur vers la structure efficace d'état de cette application.  Conserver ce pointeur mis à niveau à tout moment est essentiel pour gérer l'état global de l'application et maintenir l'intégrité de l'état de chaque module.  La gestion incorrecte de l'état global peut provoquer un comportement imprévisible de l'application.  
  
 ![Données d'état de plusieurs modules](../mfc/media/vc387n2.png "vc387N2")  
Données d'état de modules multiples  
  
 En d'autres termes, chaque module est chargé de basculer correctement entre les états du module à tous ses points d'entrée.  Un « point d'entrée » est n'importe quel emplacement où le flux d'exécution peut écrire le code du module.  Les points d'entrée sont les suivants :  
  
-   [Fonctions exportées dans une DLL](../mfc/exported-dll-function-entry-points.md)  
  
-   [Fonctions membres des interfaces COM](../mfc/com-interface-entry-points.md)  
  
-   [Procédures de fenêtre](../mfc/window-procedure-entry-points.md)  
  
## Voir aussi  
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)