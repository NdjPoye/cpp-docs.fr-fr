---
title: "CRichEditCntrItem Class | Microsoft Docs"
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
  - "CRichEditCntrItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCntrItem class"
  - "OLE items, in rich edit views"
  - "contrôles RichEdit, OLE items"
  - "contrôles RichEdit, using"
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRichEditCntrItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avec [CRichEditView](../../mfc/reference/cricheditview-class.md) et [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), fournit les fonctionnalités du contrôle RichEdit dans le contexte de l'architecture de vue du document MFC.  
  
## Syntaxe  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](../Topic/CRichEditCntrItem::CRichEditCntrItem.md)|Construit un objet `CRichEditCntrItem`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](../Topic/CRichEditCntrItem::SyncToRichEditObject.md)|Active l'élément comme un autre type.|  
  
## Notes  
 Un « contrôle RichEdit » est une fenêtre dans laquelle l'utilisateur peut entrer et modifier le texte.  Le texte peut être assigné le caractère et la mise en forme de paragraphe, et peut inclure des objets OLE incorporé.  Les contrôles richedit fournissent une interface de programmation pour le texte de mise en forme.  Toutefois, une application doit implémenter tous les composants d'interface utilisateur nécessaires pour rendre les opérations de mise en forme disponibles à l'utilisateur.  
  
 `CRichEditView` met à jour le texte et la mise en forme caractéristiques du texte.  `CRichEditDoc` met à jour la liste des éléments OLE client qui sont dans la vue.  `CRichEditCntrItem` permet d'accéder au complément aux conteneurs élément OLE client.  
  
 Les contrôles communs Windows \(et par conséquent [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) et les classes connexes\) est disponible uniquement aux programmes s'exécutant sous les versions de Windows 3,51 95\/98 et Windows NT et versions ultérieures.  
  
 Pour obtenir un exemple d'utilisation de riches modifier des éléments de conteneur dans une application MFC, consultez l'exemple d'application de [WORDPAD](../../top/visual-cpp-samples.md) .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## Configuration requise  
 **Header:** afxrich.h  
  
## Voir aussi  
 [exemple MFC WORDPAD](../../top/visual-cpp-samples.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc Class](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)