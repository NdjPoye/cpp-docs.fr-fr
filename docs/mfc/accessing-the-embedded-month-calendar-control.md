---
title: "Acc&#232;s au contr&#244;le Month Calendar Control incorpor&#233; | Microsoft Docs"
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
  - "CDateTimeCtrl (classe), accéder au contrôle incorporé"
  - "CMonthCalCtrl (classe), modifier la police"
  - "DateTimePicker (contrôle) (MFC)"
  - "DateTimePicker (contrôle) (MFC), accéder au calendrier mensuel"
  - "calendrier mensuel (contrôles), modifier la police"
  - "calendrier mensuel (contrôles), incorporés dans le sélecteur de date et heure"
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s au contr&#244;le Month Calendar Control incorpor&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'objet incorporé de contrôle de calendrier mensuel est accessible de l'objet `CDateTimeCtrl` par un appel à la méthode [GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md).  
  
> [!NOTE]
>  Le contrôle de calendrier mensuel incorporé est utilisé uniquement lorsque le contrôle de choix de date et heure n'a pas l'ensemble de style **DTS\_UPDOWN** .  
  
 Cela est utile si vous souhaitez modifier certains attributs avant que le contrôle incorporé soit affiché.  Pour ce faire, traitez la notification **DTN\_DROPDOWN**, récupérez le contrôle calendrier mensuel \(à l'aide de [CDateTimeCtrl::GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md)\), et réalisez les modifications.  Malheureusement, le contrôle calendrier mensuel n'est pas persistant.  
  
 En d'autres termes, lorsqu'un utilisateur demande l'affichage du contrôle calendrier mensuel, un nouveau contrôle calendrier mensuel est créé \(avant la notification **DTN\_DROPDOWN** \).  Le contrôle est détruit \(après la notification **DTN\_CLOSEUP** \) lorsqu'il est ignoré par l'utilisateur.  Cela signifie que tous les attributs que vous modifiez, avant que le contrôle incorporé soit affiché, est perdu lorsque le contrôle incorporé est ignoré.  
  
 L'exemple suivant illustre cette procédure, en utilisant d'un gestionnaire pour la notification **DTN\_DROPDOWN**.  Le code change la couleur d'arrière\-plan du contrôle calendrie mensuel, par un appel à [SetMonthCalColor](../Topic/CDateTimeCtrl::SetMonthCalColor.md), en gris.  Le code est comme suit :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/CPP/accessing-the-embedded-month-calendar-control_1.cpp)]  
  
 Comme indiqué précédemment, toutes les modifications apportées aux propriétés du contrôle de calendrier mensuel sont perdues, à deux exceptions près, lorsque le contrôle incorporé est ignoré.  La première exception, les couleurs du contrôle calendrier mensuel ont déjà été décrites.  La deuxième exception est la police utilisée par le contrôle calendrier mensuel.  Vous pouvez modifier la police par défaut lors d'un appel à [CDateTimeCtrl::SetMonthCalFont](../Topic/CDateTimeCtrl::SetMonthCalFont.md), et passer le handle d'une police existante.  L'exemple suivant \(où `m_dtPicker` est l'objet de contrôle de date et d'heure\) illustre une méthode possible :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/CPP/accessing-the-embedded-month-calendar-control_2.cpp)]  
  
 Une fois que la police a été modifiée, par un appel à `CDateTimeCtrl::SetMonthCalFont`, la nouvelle police est enregistrée et utilisée la prochaine fois qu'un calendrier mensuel doit être affiché.  
  
## Voir aussi  
 [Utilisation de CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)