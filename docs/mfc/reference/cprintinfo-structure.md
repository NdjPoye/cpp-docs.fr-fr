---
title: "CPrintInfo Structure | Microsoft Docs"
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
  - "CPrintInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintInfo structure"
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPrintInfo Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stocke des informations sur un travail d'impression ou d'aperçu avant impression.  
  
## Syntaxe  
  
```  
struct CPrintInfo  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPrintInfo::GetFromPage](../Topic/CPrintInfo::GetFromPage.md)|Retourne le numéro de la première page est imprimée.|  
|[CPrintInfo::GetMaxPage](../Topic/CPrintInfo::GetMaxPage.md)|Retourne le numéro de la dernière page du document.|  
|[CPrintInfo::GetMinPage](../Topic/CPrintInfo::GetMinPage.md)|Retourne le numéro de la première page du document.|  
|[CPrintInfo::GetOffsetPage](../Topic/CPrintInfo::GetOffsetPage.md)|Retourne le nombre de pages précédant la première page d'un élément de DocObject est imprimé dans un travail d'impression combinée de DocObject.|  
|[CPrintInfo::GetToPage](../Topic/CPrintInfo::GetToPage.md)|Retourne le numéro de la dernière page est imprimée.|  
|[CPrintInfo::SetMaxPage](../Topic/CPrintInfo::SetMaxPage.md)|Définit le numéro de la dernière page du document.|  
|[CPrintInfo::SetMinPage](../Topic/CPrintInfo::SetMinPage.md)|Définit le numéro de la première page du document.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPrintInfo::m\_bContinuePrinting](../Topic/CPrintInfo::m_bContinuePrinting.md)|Contient une balise qui indique si l'infrastructure doit continuer la boucle d'impression.|  
|[CPrintInfo::m\_bDirect](../Topic/CPrintInfo::m_bDirect.md)|Contient une balise qui indique si le document est imprimé directement \(sans afficher la boîte de dialogue d'impression\).|  
|[CPrintInfo::m\_bDocObject](../Topic/CPrintInfo::m_bDocObject.md)|Contient une balise qui indique si le document est imprimé est DocObject.|  
|[CPrintInfo::m\_bPreview](../Topic/CPrintInfo::m_bPreview.md)|Contient une balise qui indique si le document est affiché un aperçu de.|  
|[CPrintInfo::m\_dwFlags](../Topic/CPrintInfo::m_dwFlags.md)|Spécifie les opérations d'impression de DocObject.|  
|[CPrintInfo::m\_lpUserData](../Topic/CPrintInfo::m_lpUserData.md)|Contient un pointeur vers une structure créée par l'utilisateur.|  
|[CPrintInfo::m\_nCurPage](../Topic/CPrintInfo::m_nCurPage.md)|Identifie le numéro de la page actuellement imprimée.|  
|[CPrintInfo::m\_nJobNumber](../Topic/CPrintInfo::m_nJobNumber.md)|Spécifie le numéro de JOB assigné par le système d'exploitation pour le travail d'impression actuelle|  
|[CPrintInfo::m\_nNumPreviewPages](../Topic/CPrintInfo::m_nNumPreviewPages.md)|Identifie le nombre de pages affichées dans la fenêtre d'aperçu ; 1 ou 2.|  
|[CPrintInfo::m\_nOffsetPage](../Topic/CPrintInfo::m_nOffsetPage.md)|Spécifie l'offset du détail page DocObject d'abord dans un travail d'impression combinée de DocObject.|  
|[CPrintInfo::m\_pPD](../Topic/CPrintInfo::m_pPD.md)|Contient un pointeur vers l'objet d' `CPrintDialog` utilisé pour la boîte de dialogue d'impression.|  
|[CPrintInfo::m\_rectDraw](../Topic/CPrintInfo::m_rectDraw.md)|Spécifie un rectangle qui définit la zone utilisable actuelle de la page.|  
|[CPrintInfo::m\_strPageDesc](../Topic/CPrintInfo::m_strPageDesc.md)|Contient une chaîne de format pour l'affichage de numéro de page.|  
  
## Notes  
 `CPrintInfo` est une structure et n'a pas de classe de base.  
  
 L'infrastructure crée un objet d' `CPrintInfo` chaque fois que la commande d'impression ou d'aperçu avant impression est sélectionnée et le perdu lorsque la commande est terminée.  
  
 `CPrintInfo` contient des informations sur le travail d'impression dans son ensemble, telles que la plage des pages d'être imprimé, et l'état actuel du travail d'impression, telle que la page actuellement imprimée.  Certaines informations sont stockées dans un objet associé de [CPrintDialog](../../mfc/reference/cprintdialog-class.md) ; cet objet contient les valeurs entrées par l'utilisateur dans la boîte de dialogue d'impression.  
  
 Un objet d' `CPrintInfo` est passé entre l'infrastructure et votre classe d'affichage pendant le processus d'impression et est utilisé pour échanger des informations entre les deux.  Par exemple, l'infrastructure signale à la classe d'affichage de la page du document à imprimer en assignant une valeur au membre d' `m_nCurPage` d' `CPrintInfo`; la classe d'affichage récupère la valeur et exécute l'impression réelle de la page spécifiée.  
  
 Un autre exemple est le cas dans lequel la longueur du document n'est pas connue jusqu'à ce qu'elle soit imprimée.  Dans ce cas, les tests de la classe d'affichage de la fin du document chaque fois qu'une page est imprimée.  Fin est atteinte, la classe d'affichage définit le membre d' `m_bContinuePrinting` d' `CPrintInfo` à **FALSE**; cela indique à l'infrastructure pour désactiver la boucle d'impression.  
  
 `CPrintInfo` est utilisé par les fonctions membres d' `CView` listé dans « consultez également. » Pour plus d'informations sur l'architecture d'impression fournie par la bibliothèque MFC, consultez [fenêtres frames](../../mfc/frame-windows.md) et [architecture Document\/Vue](../../mfc/document-view-architecture.md) et les éléments [imprimer](../../mfc/printing.md) et [imprimer : documents multipages](../../mfc/multipage-documents.md).  
  
## Hiérarchie d'héritage  
 `CPrintInfo`  
  
## Configuration requise  
 **Header:** afxext.h  
  
## Voir aussi  
 [DIBLOOK exemple MFC](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)   
 [CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md)   
 [CView::OnEndPrintPreview](../Topic/CView::OnEndPrintPreview.md)   
 [CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md)   
 [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)   
 [CView::OnPrint](../Topic/CView::OnPrint.md)