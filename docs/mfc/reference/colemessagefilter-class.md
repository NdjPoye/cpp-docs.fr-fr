---
title: "COleMessageFilter Class | Microsoft Docs"
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
  - "COleMessageFilter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications (OLE), managing interactions"
  - "COleMessageFilter class"
  - "message filters [C++]"
  - "messages (C++), OLE"
  - "OLE (C++), managing concurrency"
  - "OLE (applications) (C++), managing interactions"
  - "OLE messages"
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleMessageFilter Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère l'accès concurrentiel requis par l'interaction des applications OLE.  
  
## Syntaxe  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleMessageFilter::COleMessageFilter](../Topic/COleMessageFilter::COleMessageFilter.md)|Construit un objet `COleMessageFilter`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleMessageFilter::BeginBusyState](../Topic/COleMessageFilter::BeginBusyState.md)|Place l'application dans l'état occupé.|  
|[COleMessageFilter::EnableBusyDialog](../Topic/COleMessageFilter::EnableBusyDialog.md)|Active et désactive la boîte de dialogue qui s'affiche lorsqu'une application appelée est occupée.|  
|[COleMessageFilter::EnableNotRespondingDialog](../Topic/COleMessageFilter::EnableNotRespondingDialog.md)|Active et désactive la boîte de dialogue qui s'affiche lorsqu'une application appelée ne répond pas.|  
|[COleMessageFilter::EndBusyState](../Topic/COleMessageFilter::EndBusyState.md)|Termine l'état occupé de l'application.|  
|[COleMessageFilter::OnMessagePending](../Topic/COleMessageFilter::OnMessagePending.md)|Appelé par l'infrastructure pour traiter des messages pendant qu'un OLE appel est en cours.|  
|[COleMessageFilter::Register](../Topic/COleMessageFilter::Register.md)|Stocke le filtre de messages avec les DLL système OLE.|  
|[COleMessageFilter::Revoke](../Topic/COleMessageFilter::Revoke.md)|Révoque l'alignement de filtre de messages avec les DLL système OLE.|  
|[COleMessageFilter::SetBusyReply](../Topic/COleMessageFilter::SetBusyReply.md)|Détermine la réponse occupée de l'application à un OLE appel.|  
|[COleMessageFilter::SetMessagePendingDelay](../Topic/COleMessageFilter::SetMessagePendingDelay.md)|Détermine combien de temps l'application attend une réponse à un OLE appel.|  
|[COleMessageFilter::SetRetryReply](../Topic/COleMessageFilter::SetRetryReply.md)|Détermine la réponse de l'application appelante à une application occupée.|  
  
## Notes  
 La classe d' `COleMessageFilter` est utile dans le serveur et les applications conteneur d'édition visuelle, ainsi que les applications OLE automation.  Pour les applications serveur qui sont appelées, cette classe peut être utilisée pour rendre l'application « occupée » afin que les appels entrant d'autres applications conteneur sont annulées ou redémarrés ultérieurement.  Cette classe peut également être utilisée pour déterminer l'action à effectuer par une application appelante appelée lorsque l'application est occupée.  
  
 L'utilisation courante est pour une application serveur d'appeler [BeginBusyState](../Topic/COleMessageFilter::BeginBusyState.md) et [EndBusyState](../Topic/COleMessageFilter::EndBusyState.md) lorsqu'il est sécurisé pour un document ou un autre objet OLE accessible soit détruit.  Ces appels sont apportées dans [CWinApp::OnIdle](../Topic/CWinApp::OnIdle.md) pendant les mises à jour de l'interface utilisateur.  
  
 Par défaut, un objet d' `COleMessageFilter` est alloué lorsque l'application est initialisée.  Il peut être récupéré avec [AfxOleGetMessageFilter](../Topic/AfxOleGetMessageFilter.md).  
  
 Il s'agit d'une classe avancées ; vous devez rarement l'utiliser directement.  
  
 Pour plus d'informations, consultez l'article [serveurs : implémenter un serveur](../../mfc/servers-implementing-a-server.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleMessageFilter`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)