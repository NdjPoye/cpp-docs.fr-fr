---
title: "CHtmlEditDoc Class | Microsoft Docs"
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
  - "CHtmlEditDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditDoc class"
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlEditDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avec [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), fournit les fonctionnalités de la plateforme de modification WebBrowser dans le contexte de l'architecture Document\/Vue MFC.  
  
## Syntaxe  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHtmlEditDoc::CHtmlEditDoc](../Topic/CHtmlEditDoc::CHtmlEditDoc.md)|Construit un objet `CHtmlEditDoc`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHtmlEditDoc::GetView](../Topic/CHtmlEditDoc::GetView.md)|Récupère l'objet d' `CHtmlEditView` lié au document.|  
|[CHtmlEditDoc::IsModified](../Topic/CHtmlEditDoc::IsModified.md)|Retourne si le du contrôle WebBrowser de la vue associée contient un document qui a été modifié par l'utilisateur.|  
|[CHtmlEditDoc::OpenURL](../Topic/CHtmlEditDoc::OpenURL.md)|Ouvre une URL.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `CHtmlEditDoc`  
  
## Configuration requise  
 **Header:** afxhtml.h  
  
## Voir aussi  
 [Exemple HTMLEdit](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)