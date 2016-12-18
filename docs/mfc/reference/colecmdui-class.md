---
title: "COleCmdUI Class | Microsoft Docs"
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
  - "COleCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "COleCmdUI class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleCmdUI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente une méthode pour que MFC ne mette à jour l'état des objets interface utilisateur liés aux fonctionnalités motivées par d' `IOleCommandTarget`de votre application.  
  
## Syntaxe  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleCmdUI::COleCmdUI](../Topic/COleCmdUI::COleCmdUI.md)|Construit un objet `COleCmdUI`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleCmdUI::Enable](../Topic/COleCmdUI::Enable.md)|Définit ou espaces libres la balise de commande d'activation.|  
|[COleCmdUI::SetCheck](../Topic/COleCmdUI::SetCheck.md)|Définit l'état d'une commande à activer\/désactiver.|  
|[COleCmdUI::SetText](../Topic/COleCmdUI::SetText.md)|Retourne une chaîne de nom ou de vue de texte pour une commande.|  
  
## Notes  
 Dans une application qui n'est pas activée pour DocObjects, lorsque les affichages standard un menu de l'application, MFC gère les notifcations d' **UPDATE\_COMMAND\_UI** .  Chaque notification reçoit un objet de [CCmdUI](../../mfc/reference/ccmdui-class.md) qui peut être manipulé pour refléter l'état d'une commande particulière.  Toutefois, lorsque votre application est activée de DocObjects, les notifications d' **UPDATE\_OLE\_COMMAND\_UI** de processus MFC et assigne des objets d' `COleCmdUI` .  
  
 `COleCmdUI` permet à DocObject pour accepter les commandes qui proviennent de l'interface utilisateur de son conteneur \(telle que FileNew, ouvrez, copie, etc.\), et permet à un conteneur pour accepter les commandes qui proviennent de l'interface utilisateur de DocObject.  Bien qu' `IDispatch` peut être utilisé pour distribuer les mêmes commandes, `IOleCommandTarget` offre un moyen plus simple d'interroger et exécuter parce qu'il repose sur un jeu standard de commandes, généralement sans arguments, et aucune information de type est impliqué.  `COleCmdUI` peut être utilisé pour activer, mettre à jour, et définir d'autres propriétés des commandes d'interface utilisateur de DocObject.  Lorsque vous souhaitez appeler la commande, appelez [COleServerDoc::OnExecOleCmd](../Topic/COleServerDoc::OnExecOleCmd.md).  
  
 Pour plus d'informations sur DocObjects, consultez [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) et le [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md).  Voir aussi [Premières étapes Internet : documents actifs](../../mfc/active-documents-on-the-internet.md) et le [documents actifs](../../mfc/active-documents-on-the-internet.md).  
  
## Hiérarchie d'héritage  
 [CCmdUI](../../mfc/reference/ccmdui-class.md)  
  
 `COleCmdUI`  
  
## Configuration requise  
 **Header:** afxdocobj.h  
  
## Voir aussi  
 [CCmdUI Class](../../mfc/reference/ccmdui-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)