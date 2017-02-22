---
title: "COleControlModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControlModule class"
  - "control modules"
  - "MFC ActiveX controls, OLE control modules"
  - "OLE control modules"
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleControlModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base dont vous dérivez un objet de module de contrôle OLE.  
  
## Syntaxe  
  
```  
class COleControlModule : public CWinApp  
```  
  
## Notes  
 Cette classe fournit les fonctions membres pour initialiser votre package de commande.  Chaque package de contrôle OLE qui utilise les classes MFC \(Microsoft Foundation peut uniquement contenir un objet dérivé d' `COleControlModule`.  Cet objet est généré lorsque d'autres objets globaux C\+\+ sont construits.  Déclarez votre objet dérivé d' `COleControlModule` au niveau global.  
  
 Pour plus d'informations sur l'utilisation de la classe d' `COleControlModule` , consultez la classe et l'article [Contrôles ActiveX](../../mfc/mfc-activex-controls.md)de [CWinApp](../../mfc/reference/cwinapp-class.md) .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## Configuration requise  
 **Header:** afxctl.h  
  
## Voir aussi  
 [exemple MFC TESTHELP](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)