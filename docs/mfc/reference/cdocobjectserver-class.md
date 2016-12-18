---
title: "CDocObjectServer Class | Microsoft Docs"
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
  - "CDocObjectServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "CDocObjectServer class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocObjectServer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente les interfaces OLE supplémentaires nécessaires pour transformer un serveur normal d' `COleDocument` en serveur complet de DocObject : `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`, et `IPrint`.  
  
## Syntaxe  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocObjectServer::CDocObjectServer](../Topic/CDocObjectServer::CDocObjectServer.md)|Construit un objet `CDocObjectServer`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocObjectServer::ActivateDocObject](../Topic/CDocObjectServer::ActivateDocObject.md)|Lance le serveur d'objet document, mais ne le affiche pas.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocObjectServer::OnActivateView](../Topic/CDocObjectServer::OnActivateView.md)|Affiche la vue de DocObject.|  
|[CDocObjectServer::OnApplyViewState](../Topic/CDocObjectServer::OnApplyViewState.md)|Restaure l'état de la vue de DocObject.|  
|[CDocObjectServer::OnSaveViewState](../Topic/CDocObjectServer::OnSaveViewState.md)|Enregistre l'état de la vue de DocObject.|  
  
## Notes  
 `CDocObjectServer` est dérivé d' `CCmdTarget` et fonctionne parfaitement au `COleServerDoc` pour exposer les interfaces.  
  
 Un document serveur de DocObject peut contenir des objets de [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) , qui représentent l'interface du serveur aux éléments de DocObject.  
  
 Pour personnaliser votre serveur de DocObject, dériver votre propre classe d' `CDocObjectServer` et remplacer son installation de vue s'exécute, [OnActivateView](../Topic/CDocObjectServer::OnActivateView.md), [OnApplyViewState](../Topic/CDocObjectServer::OnApplyViewState.md), et [OnSaveViewState](../Topic/CDocObjectServer::OnSaveViewState.md).  Vous devrez fournir une nouvelle instance de votre classe en réponse à les appels d'infrastructure.  
  
 Pour plus d'informations sur DocObjects, consultez [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) et le [COleCmdUI](../../mfc/reference/colecmdui-class.md) dans MFC *Reference*.  Voir aussi [Premières étapes Internet : documents actifs](../../mfc/active-documents-on-the-internet.md) et le [documents actifs](../../mfc/active-documents-on-the-internet.md).  
  
 Consultez également l'article de la Base de connaissances :  
  
-   Q247382 : PRB : Les info\-bulles pour les contrôles dans le serveur de document ActiveX sont masquées par le conteneur de documents ActiveX  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## Configuration requise  
 **Header:** afxdocob.h  
  
## Voir aussi  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem Class](../../mfc/reference/cdocobjectserveritem-class.md)