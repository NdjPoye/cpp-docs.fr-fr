---
title: "CSingleDocTemplate Class | Microsoft Docs"
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
  - "CSingleDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSingleDocTemplate class"
  - "modèles de document, single"
  - "interface monodocument, applications"
  - "modèles, SDI"
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSingleDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit un modèle de document qui implémente l'interface monodocument \(SDI\).  
  
## Syntaxe  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSingleDocTemplate::CSingleDocTemplate](../Topic/CSingleDocTemplate::CSingleDocTemplate.md)|Construit un objet `CSingleDocTemplate`.|  
  
## Notes  
 Une application sdi qui utilise la fenêtre frame principale pour afficher un document ; seul un document peut être ouvert à la fois.  
  
 Un modèle de document définit la relation entre trois types de classes :  
  
-   Une classe de document, que vous dérivez de **CDocument**.  
  
-   Une classe d'affichage, qui affiche des données provenant de la classe de document listé en haut.  Vous pouvez dériver cette classe d' `CView`, d' `CScrollView`, d' `CFormView`, ou d' `CEditView`.  \(Vous pouvez également utiliser `CEditView` directement.\)  
  
-   Une classe de fenêtre frame, qui contient la vue.  Pour un modèle de document \(SDI, vous pouvez dériver cette classe d' `CFrameWnd`; si vous n'avez pas besoin de personnaliser le comportement de la fenêtre frame principale, vous pouvez utiliser `CFrameWnd` directement sans dériver votre propre classe.  
  
 Une application SDI en charge en général un type de document, elle a un seul objet d' `CSingleDocTemplate` .  Seul un document peut être ouvert à la fois.  
  
 Vous n'avez pas besoin de n'appeler une fonction membre d' `CSingleDocTemplate` à l'exception de le constructeur.  L'infrastructure gère les objets d' `CSingleDocTemplate` en interne.  
  
 Pour plus d'informations sur l'utilisation `CSingleDocTemplate`, consultez [Modèles de document et le processus de création du document\/vue](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [MFC exemple DOCKTOOL](../../top/visual-cpp-samples.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate Class](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)