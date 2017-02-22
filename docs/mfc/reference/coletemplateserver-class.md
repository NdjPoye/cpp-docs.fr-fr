---
title: "COleTemplateServer Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleTemplateServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automation servers [C++], implémenter"
  - "COleTemplateServer class"
  - "link containers [C++]"
  - "OLE link containers"
  - "applications serveur OLE, COleTemplateServer class"
  - "applications serveur OLE, managing server documents"
  - "serveurs, OLE"
  - "visual editing, serveurs"
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleTemplateServer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé pour OLE de serveur d'édition visuelle, serveurs Automation, et conteneurs de lien \(applications qui prend en charge les incorporations\).  
  
## Syntaxe  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleTemplateServer::COleTemplateServer](../Topic/COleTemplateServer::COleTemplateServer.md)|Construit un objet `COleTemplateServer`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleTemplateServer::ConnectTemplate](../Topic/COleTemplateServer::ConnectTemplate.md)|Connecte un modèle de document à l'objet sous\-jacent d' `COleObjectFactory` .|  
|[COleTemplateServer::Unregister](../Topic/COleTemplateServer::Unregister.md)|Annule l'inscription le modèle de document associé.|  
|[COleTemplateServer::UpdateRegistry](../Topic/COleTemplateServer::UpdateRegistry.md)|Stocke le type de document avec le Registre système OLE.|  
  
## Notes  
 Cette classe est dérivée de la classe [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); habituellement, vous pouvez utiliser `COleTemplateServer` directement plutôt que dérivant votre propre classe.  `COleTemplateServer` utilise un objet de [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) pour gérer les documents serveur.  Utilisez `COleTemplateServer` en implémentant un serveur, c. autrement dit., un serveur qui peut être exécuté comme une application autonome.  Les serveurs entiers sont en général des applications d'interface multidocument \(MDI\), bien que des applications de \(SDI\) d'interface monodocument soient prises en charge.  Un objet d' `COleTemplateServer` est nécessaire pour chaque type de document serveur d'application prend en charge ; autrement dit, si votre application serveur prend en charge les feuilles de calcul et des graphiques, vous devez avoir deux objets d' `COleTemplateServer` .  
  
 `COleTemplateServer` substitue la fonction membre d' `OnCreateInstance` définie par `COleObjectFactory`.  Cette fonction membre est appelée par l'infrastructure pour créer un objet C\+\+ du type approprié.  
  
 Pour plus d'informations sur les serveurs, consultez l'article [serveurs : implémenter un serveur](../../mfc/servers-implementing-a-server.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## Configuration requise  
 **Header:** afxdisp.h  
  
## Voir aussi  
 [exemple MFC HIERSVR](../../top/visual-cpp-samples.md)   
 [COleObjectFactory Class](../../mfc/reference/coleobjectfactory-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)