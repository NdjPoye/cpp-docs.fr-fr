---
title: "Gestionnaires de zones de liste | Microsoft Docs"
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
  - "ON_LBN_DBLCLK"
  - "ON_LBN_ERRSPACE"
  - "ON_LBN_SETFOCUS"
  - "ON_LBN_SELCHANGE"
  - "ON_LBN_KILLFOCUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "zones de liste, gestionnaires de zones de liste"
  - "ON_LBN_DBLCLK"
  - "ON_LBN_ERRSPACE"
  - "ON_LBN_KILLFOCUS"
  - "ON_LBN_SELCHANGE"
  - "ON_LBN_SETFOCUS"
ms.assetid: e4e54412-2167-436a-883b-5dcad01820b8
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestionnaires de zones de liste
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les entrées de mappage suivantes ont le prototype de la fonction correspondant.  
  
|Entrée de carte|Prototype de fonction|  
|---------------------|---------------------------|  
|ON\_LBN\_DBLCLK \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_LBN\_ERRSPACE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_LBN\_KILLFOCUS \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_LBN\_SELCHANGE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_LBN\_SETFOCUS \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
  
## Voir aussi  
 [Tables des messages](../../mfc/reference/message-maps-mfc.md)