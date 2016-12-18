---
title: "CDynamicChain Class | Microsoft Docs"
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
  - "ATL::CDynamicChain"
  - "ATL.CDynamicChain"
  - "CDynamicChain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicChain class"
  - "chaining message maps"
  - "message maps, enchaîner"
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicChain Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes qui prend en charge le chaînage dynamique des tables des messages.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CDynamicChain  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDynamicChain::CDynamicChain](../Topic/CDynamicChain::CDynamicChain.md)|Constructeur.|  
|[CDynamicChain::~CDynamicChain](../Topic/CDynamicChain::~CDynamicChain.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDynamicChain::CallChain](../Topic/CDynamicChain::CallChain.md)|Dirige une boîte de message windows à la table des messages d'un autre objet.|  
|[CDynamicChain::RemoveChainEntry](../Topic/CDynamicChain::RemoveChainEntry.md)|Supprime une entrée de la table des messages de la collection.|  
|[CDynamicChain::SetChainEntry](../Topic/CDynamicChain::SetChainEntry.md)|Ajoute une entrée de la table des messages à la collection ou modifie une entrée existante.|  
  
## Notes  
 `CDynamicChain` gère une collection de tables des messages, ce qui permet à un message windows pour être exécuté, au moment de l'exécution, la table des messages d'un autre objet.  
  
 Pour ajouter la prise en charge du chaînage dynamique des tables des messages, procédez comme suit :  
  
-   Dérivez votre classe d' `CDynamicChain`.  Dans la table des messages, spécifiez la macro de [CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md) pour chaîner à la table des messages par défaut d'un autre objet.  
  
-   Dérivez chaque classe que vous souhaitez chaîner valeur de [CMessageMap](../../atl/reference/cmessagemap-class.md).  `CMessageMap` permet à un objet d'exposer ses tables des messages à d'autres objets.  
  
-   Appelez `CDynamicChain::SetChainEntry` pour l'identifier auquel l'objet et à laquelle la table des messages vous souhaitez chaînage.  
  
 Par exemple, supposez que votre classe est définie comme suit :  
  
 [!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/CPP/cdynamicchain-class_1.h)]  
  
 Le client appelle ensuite `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/CPP/cdynamicchain-class_2.cpp)]  
  
 où est l'objet `chainedObj` chaîné et est une instance d'une classe dérivée d' `CMessageMap`.  Maintenant, si `myCtl` reçoit un message qui n'est pas géré par `OnPaint` ou `OnSetFocus`, la procédure de fenêtre dirige le message à la table des messages par défaut d'`chainedObj`.  
  
 Pour plus d'informations sur le chaînage de table des messages, consultez [tables des messages](../../atl/message-maps-atl.md) dans l'article « classes de fenêtres ATL. »  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [CWindowImpl Class](../../atl/reference/cwindowimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)