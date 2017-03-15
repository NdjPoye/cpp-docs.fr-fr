---
title: "Gestionnaires d&#233;finis par l&#39;utilisateur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.handlers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_MESSAGE (macro)"
  - "ON_REGISTERED_MESSAGE (macro)"
  - "gestionnaires définis par l'utilisateur"
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Gestionnaires d&#233;finis par l&#39;utilisateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les entrées de map suivantes correspondent aux prototypes de fonction.  
  
|Entrée de map|Prototype de fonction|  
|-------------------|---------------------------|  
|ON\_MESSAGE \( \<message\>, \<memberFxn\> \)|memberFxn de l'afx\_msg LRESULT \(WPARAM, LPARAM\) ;|  
|SUR\_MESSAGE\_ENREGISTRE \( \<nMessageVariable\>, \<memberFxn\> \)|memberFxn de l'afx\_msg LRESULT \(WPARAM, LPARAM\) ;|  
|ON\_THREAD\_MESSAGE \( \<message\>, \<memberFxn\> \)|memberFxn void d'afx\_msg \(WPARAM, LPARAM\) ;|  
|SUR\_MESSAGE\_THREAD\_ENREGISTRE \( \<nMessageVariable\>, \<memberFxn\> \)|memberFxn void d'afx\_msg \(WPARAM, LPARAM\) ;|  
  
## Voir aussi  
 [Tables des messages](../../mfc/reference/message-maps-mfc.md)   
 [Gestionnaires de messages WM\_](../../mfc/reference/handlers-for-wm-messages.md)