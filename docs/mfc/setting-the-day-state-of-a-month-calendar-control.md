---
title: "D&#233;finition de l&#39;&#233;tat du jour d&#39;un contr&#244;le month calendar | Microsoft Docs"
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
  - "MCN_GETDAYSTATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl (classe), définir les informations sur l'état du jour"
  - "MCN_GETDAYSTATE (notification)"
  - "calendrier mensuel (contrôles), informations sur l'état du jour"
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finition de l&#39;&#233;tat du jour d&#39;un contr&#244;le month calendar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un des attributs d'un contrôle calendrier mensuel est la possibilité de stocker des informations, connues sous le nom d'état jour du contrôle, pour chaque jour du mois.  Ces informations sont utilisées pour mettre en évidence des dates du mois actuellement affiché.  
  
> [!NOTE]
>  L'objet `CMonthCalCtrl` doit avoir le style **MCS\_DAYSTATE** pour afficher les informations d'état jour.  
  
 Les informations d'état jour sont exprimées en tant que type de données 32 bits, **MONTHDAYSTATE**.  Chaque bit dans un champ **MONTHDAYSTATE** \(1 à 31\) représente l'état d'un jour du mois.  Si un bit est activé, le jour correspondant s'affiche en gras ; sinon il s'affiche sans l'accentuation.  
  
 Il existe deux méthodes pour définir l'état jour du contrôle calendrier mensuel : explicitement par un appel à [CMonthCalCtrl::SetDayState](../Topic/CMonthCalCtrl::SetDayState.md) ou par la gestion du message de notification **MCN\_GETDAYSTATE**.  
  
## Gérer le message de notification de MCN\_GETDAYSTATE  
 Le message **MCN\_GETDAYSTATE** est envoyé par le contrôle pour déterminer comment les jours dans les mois visibles doivent être affiché.  
  
> [!NOTE]
>  Le contrôle cache les mois précédents et suivants, et en ce qui concerne le mois visible, vous recevez cette notification chaque fois qu'un nouveau mois est choisi.  
  
 Pour traiter correctement ce message, vous devez déterminer les informations d'état jour pour le nombre de mois demandé, initialiser un tableau de structures **MONTHDAYSTATE** avec les valeurs appropriées, et initialiser le membre de structure associé avec les nouvelles informations.  La procédure suivante, détaillant les étapes nécessaires, suppose que vous avez un objet `CMonthCalCtrl` appelé `m_monthcal` et un tableau d'objets **MONTHDAYSTATE**, `mdState`.  
  
#### Gérer le message de notification de MCN\_GETDAYSTATE  
  
1.  Dans la fenêtre Propriétés, ajoutez un gestionnaire de notification du message **MCN\_GETDAYSTATE** à l'objet `m_monthcal` \(voir [Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
2.  Dans le corps du gestionnaire, ajoutez le code suivant :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/CPP/setting-the-day-state-of-a-month-calendar-control_1.cpp)]  
  
     L'exemple suivant convertit le pointeur `pNMHDR` en type approprié, puis détermine le nombre de mois pour lequel les informations sont demandées \(`pDayState->cDayState`\).  Pour chaque mois, le champ de bits actuel \(`pDayState->prgDayState[i]`\) est initialisé à zéro et les dates nécessaires sont assignées \(dans ce cas, le 15 de chaque mois\).  
  
## Voir aussi  
 [Utilisation de CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)