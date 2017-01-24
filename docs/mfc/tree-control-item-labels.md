---
title: "&#201;tiquettes d&#39;&#233;l&#233;ment de contr&#244;le d&#39;arborescence | Microsoft Docs"
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
  - "CTreeCtrl (classe), étiquettes d'élément"
  - "étiquettes d'élément"
  - "étiquettes d'élément, contrôles d'arborescence"
  - "étiquettes, CTreeCtrl (éléments)"
  - "contrôles d'arborescence, étiquettes d'élément"
ms.assetid: fe834107-1a25-4280-aced-774c11565805
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;tiquettes d&#39;&#233;l&#233;ment de contr&#244;le d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous spécifiez en général le texte de l'étiquette d'un élément en ajoutant l'élément dans le contrôle tree \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\).  La fonction membre `InsertItem` peut passer une structure [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) qui définit les propriétés de l'élément, y compris une chaîne contenant le texte de l'étiquette.  `InsertItem` a plusieurs surcharges qui peuvent être appelées avec diverses combinaisons de paramètres.  
  
 Un contrôle d'arborescence alloue de la mémoire pour stocker chaque élément ; le texte des étiquettes d'élément prend une partie significative de la mémoire.  Si votre application conserve une copie de chaînes dans l'arborescence, il est possible de réduire les besoins en mémoire du contrôle en spécifiant la valeur de **LPSTR\_TEXTCALLBACK** dans le membre de **pszText** `TV_ITEM` ou le paramètre `lpszItem` au lieu de passer les chaînes réelles au contrôle d'arborescence.  L'utilisation de **LPSTR\_TEXTCALLBACK** fait que l'arborescence récupère le texte de l'étiquette de l'élément de l'application lorsque l'élément doit être repeint.  Pour récupérer le texte, l'arborescence envoie un message de notification [TVN\_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518), qui inclut notamment l'adresse d'une structure [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418).  Vous devez répondre en définissant les membres appropriés de la structure incluse.  
  
 Un contrôle d'arborescence utilise de la mémoire allouée du tas du processus qui crée l'arborescence.  Le nombre maximal d'éléments dans un contrôle d'arborescence est basé sur la quantité de mémoire disponible dans le tas.  Chaque élément occupe 64 octets.  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)