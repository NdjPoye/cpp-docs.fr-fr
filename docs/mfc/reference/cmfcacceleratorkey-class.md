---
title: "CMFCAcceleratorKey Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCAcceleratorKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAcceleratorKey class"
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: 36
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCAcceleratorKey Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe d'assistance qui implémente le mappage principal virtuel et la mise en forme.  
  
## Syntaxe  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](../Topic/CMFCAcceleratorKey::CMFCAcceleratorKey.md)|Construit un objet `CMFCAcceleratorKey`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCAcceleratorKey::Format](../Topic/CMFCAcceleratorKey::Format.md)|Traduit la structure d'ACCEL en sa représentation visuelle.|  
|[CMFCAcceleratorKey::SetAccelerator](../Topic/CMFCAcceleratorKey::SetAccelerator.md)|Définit la touche de raccourci de l'objet d' `CMFCAcceleratorKey` .|  
  
## Notes  
 Les touches accélérateur sont également appelées des touches de raccourci.  Si vous souhaitez afficher les raccourcis clavier qu'un utilisateur entre dans le, [CMFCAcceleratorKeyAssignCtrl Class](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) mappe les raccourcis clavier, par exemple Alt\+Shift\+S, un format de texte personnalisé, tel que « ALT \+ décalage \+ S ».  Chaque tables d'objets d' `CMFCAcceleratorKey` une touche de raccourci unique dans un format texte.  
  
 Pour plus d'informations sur l'utilisation des touches de raccourci et les tables d'accélérateurs, consultez l'[CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md).  
  
## Exemple  
 L'exemple suivant montre comment construire un objet d' `CMFCAcceleratorKey` et comment utiliser sa méthode d' `Format` .  
  
 [!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/CPP/cmfcacceleratorkey-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)  
  
## Configuration requise  
 **en\-tête :** afxacceleratorkey.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)