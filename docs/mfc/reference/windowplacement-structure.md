---
title: "WINDOWPLACEMENT, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WINDOWPLACEMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WINDOWPLACEMENT (structure)"
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# WINDOWPLACEMENT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure d'`WINDOWPLACEMENT` contient des informations sur la position d'un point dans l'écran**.**  
  
## Syntaxe  
  
```  
  
      typedef struct tagWINDOWPLACEMENT {     /* wndpl */  
   UINT length;  
   UINT flags;  
   UINT showCmd;  
   POINT ptMinPosition;  
   POINT ptMaxPosition;  
   RECT rcNormalPosition;  
} WINDOWPLACEMENT;  
```  
  
#### Paramètres  
 *length*  
 Spécifie la taille de la structure  en octets.  
  
 `flags`  
 Spécifie les indicateurs qui contrôlent la position de la fenêtre réduite et la méthode par laquelle la fenêtre est restaurée.  Ce membre peut être l'une ou deux tous les indicateurs suivants :  
  
-   **WPF\_SETMINPOSITION** spécifie que les valeurs x et O\- les positions de la fenêtre réduite peut être spécifié **.** Cet indicateur doit être spécifié si les coordonnées sont spécifiées dans le membre de **ptMinPosition**.  
  
-   **WPF\_RESTORETOMAXIMIZED** spécifie que la fenêtre restaurée est optimisée, qu'il s'il a été agrandi pour qu'elle a été réduit.  Ce paramètre est valide uniquement la prochaine fois que la fenêtre est restaurée.  Elle ne modifie pas le comportement par défaut de restauration.  Cet indicateur est valide uniquement lorsque la valeur de **SW\_SHOWMINIMIZED** est spécifiée pour le membre de **showCmd**.  
  
 *ShowCmd*  
 Spécifie l'état actuel de l'environnement.  Ce membre peut avoir l'une des valeurs suivantes :  
  
-   **SW\_HIDE** masque la fenêtre et passe l'activation dans une autre fenêtre.  
  
-   **SW\_MINIMIZE** réduit également la fenêtre spécifiée et active la fenêtre de niveau supérieur dans la liste du système.  
  
-   **SW\_RESTORE** active et affiche la fenêtre.  Si la fenêtre est réduite ou optimisée, windows la restaurer à sa taille d'origine et position \(même que **SW\_SHOWNORMAL**\).  
  
-   **SW\_SHOW** active une fenêtre et l'affiche dans sa taille et de position actuelle.  
  
-   **SW\_SHOWMAXIMIZED** active une fenêtre et l'affiche dans une fenêtre optimisée.  
  
-   **SW\_SHOWMINIMIZED** active une fenêtre et l'affiche dans l'icône.  
  
-   **SW\_SHOWMINNOACTIVE** affiche une fenêtre comme icône.  La fenêtre actuellement active reste active.  
  
-   **SW\_SHOWNA** affiche la fenêtre dans son état actuel.  La fenêtre actuellement active reste active.  
  
-   **SW\_SHOWNOACTIVATE** affiche la fenêtre dans sa taille et de position plus récentes.  La fenêtre actuellement active reste active.  
  
-   **SW\_RESTORE** active et affiche la fenêtre.  Si la fenêtre est réduite ou optimisée, Windows la restaure à sa taille d'origine et position \(même que **SW\_SHOWNORMAL**\).  
  
 *ptMinPosition*  
 Spécifie la position de l'angle supérieur gauche de la fenêtre lorsque la fenêtre est réduite.  
  
 `ptMaxPosition`  
 Spécifie la position de l'angle supérieur gauche de la fenêtre lorsque la fenêtre est réduite.  
  
 *rcNormalPosition*  
 Spécifie les détails de la fenêtre lorsque la fenêtre est en position \(restaurée\) standard.  
  
## Configuration requise  
 **En\-tête :** winuser.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../Topic/CWnd::SetWindowPlacement.md)