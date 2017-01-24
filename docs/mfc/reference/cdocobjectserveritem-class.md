---
title: "CDocObjectServerItem Class | Microsoft Docs"
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
  - "CDocObjectServerItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "CDocObjectServerItem class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocObjectServerItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE verbes du serveur d'outils spécifiquement pour les serveurs de DocObject.  
  
## Syntaxe  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](../Topic/CDocObjectServerItem::CDocObjectServerItem.md)|Construit un objet `CDocObjectServerItem`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocObjectServerItem::GetDocument](../Topic/CDocObjectServerItem::GetDocument.md)|Extrait un pointeur vers le document qui contient l'élément.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocObjectServerItem::OnHide](../Topic/CDocObjectServerItem::OnHide.md)|Lève une exception si les tests d'infrastructure pour masquer un élément de DocObject.|  
|[CDocObjectServerItem::OnShow](../Topic/CDocObjectServerItem::OnShow.md)|Appelé par l'infrastructure pour rendre l'élément de DocObject actif sur place.  Si l'élément n'est pas DocObject, appelle [COleServerItem::OnShow](../Topic/COleServerItem::OnShow.md).|  
  
## Notes  
 `CDocObjectServerItem` définit les fonctions membres substituables : [OnHide](../Topic/CDocObjectServerItem::OnHide.md), [OnOpen](http://msdn.microsoft.com/fr-fr/7a9b1363-6ad8-4732-9959-4e35c07644fd), et [OnShow](../Topic/CDocObjectServerItem::OnShow.md).  
  
 Pour utiliser `CDocObjectServerItem`, assurez que la substitution d' [OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md) dans votre `COleServerDoc`\- la classe dérivée retourne un nouvel objet d' `CDocObjectServerItem` .  Si vous devez changer toute fonctionnalité dans votre élément, vous pouvez créer une nouvelle instance de votre propre `CDocObjectServerItem`classe dérivée.  
  
 Pour plus d'informations sur DocObjects, consultez [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) et le [COleCmdUI](../../mfc/reference/colecmdui-class.md) dans MFC *Reference*.  Voir aussi [Premières étapes Internet : documents actifs](../../mfc/active-documents-on-the-internet.md) et le [documents actifs](../../mfc/active-documents-on-the-internet.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## Configuration requise  
 **Header:** afxdocob.h  
  
## Voir aussi  
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer Class](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem Class](../../mfc/reference/coledocobjectitem-class.md)