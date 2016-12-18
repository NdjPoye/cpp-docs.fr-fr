---
title: "ID de fen&#234;tre et commande standard | Microsoft Docs"
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
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ID de fenêtre et commande standard"
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ID de fen&#234;tre et commande standard
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La bibliothèque MFC définit le nombre d'identificateurs standard de commande et de fenêtre dans Afxres.h.  Ces ID sont utilisés le plus souvent dans les éditeurs de ressources et la fenêtre Propriétés pour mapper des messages à vos fonctions de gestion.  Toutes les commandes standard ont le préfixe **ID\_**.  Par exemple, lorsque vous utilisez l'éditeur de menu, vous liez généralement l'élément de menu ouverture de fichier à l'identificateur standard de commande de `ID_FILE_OPEN`  
  
 Pour la plupart des commandes standard, le code de l'application n'a pas besoin de faire référence à l'ID de commande, car l'infrastructure elle\-même gère les commandes dans des tables des messages dans ses classes principales d'infrastructure \(`CWinThread`, `CWinApp`, `CView`, **CDocument**, etc.\).  
  
 Outre les identificateurs standards de commande, il définit plusieurs autres identificateurs standard qui ont le préfixe **AFX\_ID**.  Ces ID sont des identificateurs standard de la fenêtre \(préfixe **AFX\_IDW\_**\), ID de chaîne \(préfixe **AFX\_IDS\_**\), et plusieurs autres types.  
  
 Les ID qui commencent par le préfixe **AFX\_ID** sont souvent utilisés par les programmeurs, mais doivent faire référence aux ID en remplaçant les fonctions cadres qui font également référence à **AFX\_ID**s.  
  
 Les ID ne sont pas documentés individuellement dans cette référence.  Vous pouvez trouver plus d'informations sur ces derniers dans les notes techniques de [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), et [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Le fichier d'en\-tête Afxres.h est indirectement inclus dans Afxwin.h.  Vous devez explicitement inclure l'instruction suivante dans le fichier de script de ressources de votre application \(.rc\) :  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/CPP/standard-command-and-window-ids_1.h)]  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)