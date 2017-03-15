---
title: "Gestionnaires de zone de liste d&#233;roulante | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_CBN_KILLFOCUS"
  - "ON_CBN_ERRSPACE"
  - "ON_CBN_EDITCHANGE"
  - "ON_CBN_CLOSEUP"
  - "ON_CBN_DBLCLK"
  - "ON_CBN_EDITUPDATE"
  - "ON_CBN_DROPDOWN"
  - "ON_CBN_SELENDOK"
  - "ON_CBN_SELCHANGE"
  - "ON_CBN_SETFOCUS"
  - "ON_CBN_SELENDCANCEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "zones de liste déroulante, gestionnaires"
  - "ON_CBN_CLOSEUP"
  - "ON_CBN_DBLCLK"
  - "ON_CBN_DROPDOWN"
  - "ON_CBN_EDITCHANGE"
  - "ON_CBN_EDITUPDATE"
  - "ON_CBN_ERRSPACE"
  - "ON_CBN_KILLFOCUS"
  - "ON_CBN_SELCHANGE"
  - "ON_CBN_SELENDCANCEL"
  - "ON_CBN_SELENDOK"
  - "ON_CBN_SETFOCUS"
ms.assetid: 7f092412-01b7-4242-95ec-41ba506b9d71
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Gestionnaires de zone de liste d&#233;roulante
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les entrées de mappage suivantes correspondent aux prototypes de fonction.  
  
|Entrée de mappage|Prototype de fonction|  
|-----------------------|---------------------------|  
|ON\_CBN\_CLOSEUP \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_DBLCLK \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_DROPDOWN \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_EDITCHANGE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_EDITUPDATE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_ERRSPACE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_KILLFOCUS \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SELCHANGE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SELENDCANCEL \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SELENDOK \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SETFOCUS \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
  
## Voir aussi  
 [Tables des messages](../../mfc/reference/message-maps-mfc.md)