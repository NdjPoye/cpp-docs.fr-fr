---
title: "CMessageMap Class | Microsoft Docs"
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
  - "CMessageMap"
  - "ATL.CMessageMap"
  - "ATL::CMessageMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, gestionnaires de messages"
  - "CMessageMap class"
  - "message maps, ATL"
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMessageMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe permet aux tables des messages d'un objet pour être accès par un autre objet.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class ATL_NO_VTABLE CMessageMap  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMessageMap::ProcessWindowMessage](../Topic/CMessageMap::ProcessWindowMessage.md)|Accède à une table des messages dans `CMessageMap`classe dérivée.|  
  
## Notes  
 `CMessageMap` est une classe de base abstraite qui fournit les tables des messages d'un objet soient accessibles par un autre objet.  Pour qu'un objet expose ses tables des messages, la classe doit dériver d' `CMessageMap`.  
  
 ATL utilise `CMessageMap` pour prendre en charge les fenêtres contenues et le chaînage dynamique de table des messages.  Par exemple, une classe contenant un objet de [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) doit dériver d' `CMessageMap`.  Le code suivant est pris de l'exemple de [SUBEDIT](../../top/visual-cpp-samples.md) .  Par [CComControl](../../atl/reference/ccomcontrol-class.md), la classe d' `CAtlEdit` dérive automatiquement d' `CMessageMap`.  
  
 [!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/CPP/cmessagemap-class_1.h)]  
  
 Étant donné que la fenêtre contenue, `m_EditCtrl`, utilise une table des messages dans la classe conteneur, `CAtlEdit` dérive d' `CMessageMap`.  
  
 Pour plus d'informations sur les tables des messages, consultez [tables des messages](../../atl/message-maps-atl.md) dans l'article « classes de fenêtres ATL. »  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [CDynamicChain Class](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)