---
title: "CRichEditDoc Class | Microsoft Docs"
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
  - "CRichEditDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditDoc class"
  - "document/view architecture, contrôles RichEdit"
  - "documents, rich edit"
  - "OLE containers, rich edit"
  - "contrôles RichEdit, OLE container"
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRichEditDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avec [CRichEditView](../../mfc/reference/cricheditview-class.md) et [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), fournit les fonctionnalités du contrôle RichEdit dans le contexte de l'architecture de vue du document MFC.  
  
## Syntaxe  
  
```  
  
class CRichEditDoc : public COleServerDoc  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRichEditDoc::CreateClientItem](../Topic/CRichEditDoc::CreateClientItem.md)|Appelé pour effectuer un nettoyage du document.|  
|[CRichEditDoc::GetStreamFormat](../Topic/CRichEditDoc::GetStreamFormat.md)|Indique si l'entrée et de sortie de flux doit inclure des informations de mise en forme.|  
|[CRichEditDoc::GetView](../Topic/CRichEditDoc::GetView.md)|Récupère l'objet asssociated de [CRichEditView](../../mfc/reference/cricheditview-class.md) .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRichEditDoc::m\_bRTF](../Topic/CRichEditDoc::m_bRTF.md)|Indique si l'E\/S de flux de données doit inclure la mise en forme.|  
  
## Notes  
 Un « contrôle RichEdit » est une fenêtre dans laquelle l'utilisateur peut entrer et modifier le texte.  Le texte peut être assigné le caractère et la mise en forme de paragraphe, et peut inclure des objets OLE incorporé.  Les contrôles richedit fournissent une interface de programmation pour le texte de mise en forme.  Toutefois, une application doit implémenter tous les composants d'interface utilisateur nécessaires pour rendre les opérations de mise en forme disponibles à l'utilisateur.  
  
 `CRichEditView` met à jour le texte et la mise en forme caractéristiques du texte.  `CRichEditDoc` met à jour la liste d'éléments clients qui sont dans la vue.  `CRichEditCntrItem` permet aux conteneurs d'accéder aux éléments OLE côté client.  
  
 Les contrôles communs Windows \(et par conséquent [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) et les classes connexes\) est disponible uniquement aux programmes s'exécutant sous les versions de Windows 3,51 95\/98 et Windows NT et versions ultérieures.  
  
 Pour obtenir un exemple d'utilisation d'un document riche de modification dans une application MFC, consultez l'exemple d'application de [WORDPAD](../../top/visual-cpp-samples.md) .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## Configuration requise  
 **Header:** afxrich.h  
  
## Voir aussi  
 [exemple MFC WORDPAD](../../top/visual-cpp-samples.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem Class](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl Class](../../mfc/reference/cricheditctrl-class.md)