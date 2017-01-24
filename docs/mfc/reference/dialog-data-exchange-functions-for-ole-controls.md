---
title: "Fonctions d&#39;&#233;change de donn&#233;es de bo&#238;tes de dialogue pour contr&#244;les OLE | Microsoft Docs"
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
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DDX (échange de données de boîtes de dialogue), prise en charge OLE"
  - "contrôles OLE, DDX (fonctions)"
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions d&#39;&#233;change de donn&#233;es de bo&#238;tes de dialogue pour contr&#244;les OLE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique répertorie les fonctions de DDX\_OC utilisées pour échanger des données entre une propriété d'un contrôle OLE dans un objet boîte de dialogue, une vue formulaire, ou une vue de contrôle et un membre de données de la boîte de dialogue, de la vue formulaire, ou de la vue de contrôle.  
  
### Fonctions DDX\_OC  
  
|||  
|-|-|  
|[DDX\_OCBool](../Topic/DDX_OCBool.md)|Gère le transfert de données de **BOOL** entre la propriété d'un contrôle OLE et un membre de données **BOOL**.|  
|[DDX\_OCBoolRO](../Topic/DDX_OCBoolRO.md)|Gère le transfert de données **BOOL** entre la propriété en lecture seule d'un contrôle OLE et un membre de données **BOOL**.|  
|[DDX\_OCColor](../Topic/DDX_OCColor.md)|Gère le transfert des données **OLE\_COLOR** entre la propriété d'un contrôle OLE et un membre de données **OLE\_COLOR**.|  
|[DDX\_OCColorRO](../Topic/DDX_OCColorRO.md)|Gère le transfert des données **OLE\_COLOR** entre la propriété en lecture seule d'un contrôle OLE et un membre de données **OLE\_COLOR**.|  
|[DDX\_OCFloat](../Topic/DDX_OCFloat.md)|Gère le transfert de données **float** \(ou **double**\) entre la propriété d'un contrôle OLE et un membre de données **float** \(ou **double**\).|  
|[DDX\_OCFloatRO](../Topic/DDX_OCFloatRO.md)|Gère le transfert de données **float** \(ou **double**\) entre la propriété en lecture seule d'un contrôle OLE et un membre de données **float** \(ou **double**\).|  
|[DDX\_OCInt](../Topic/DDX_OCInt.md)|Gère le transfert des données `int` \(ou **long**\) entre la propriété d'un contrôle OLE et un membre de données `int` \(ou **long**\).|  
|[DDX\_OCIntRO](../Topic/DDX_OCIntRO.md)|Gère le transfert des données `int` \(ou **long**\) entre la propriété en lecture seule d'un contrôle OLE et un membre de données `int` \(ou **long**\).|  
|[DDX\_OCShort](../Topic/DDX_OCShort.md)|Gère le transfert de données **short** entre la propriété d'un contrôle OLE et un membre de données **short**.|  
|[DDX\_OCShortRO](../Topic/DDX_OCShortRO.md)|Gère le transfert de données **short** entre la propriété en lecture seule d'un contrôle OLE et un membre de données **short**.|  
|[DDX\_OCText](../Topic/DDX_OCText.md)|Gère le transfert de données **CString**  entre la propriété d'un contrôle OLE et un membre de données **CString** .|  
|[DDX\_OCTextRO](../Topic/DDX_OCTextRO.md)|Gère le transfert de données **CString**  entre la propriété en lecture seule d'un contrôle OLE et un membre de données **CString** .|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)