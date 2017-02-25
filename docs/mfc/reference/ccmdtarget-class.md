---
title: "CCmdTarget Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCmdTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCmdTarget class"
  - "routage des commandes, command targets"
  - "command targets"
  - "message maps, CCmdTarget base class"
  - "cibles, commande"
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CCmdTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base pour l'architecture de table des messages de bibliothèque MFC.  
  
## Syntaxe  
  
```  
class CCmdTarget : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CCmdTarget::CCmdTarget](../Topic/CCmdTarget::CCmdTarget.md)|Construit un objet `CCmdTarget`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md)|Affiche le curseur en tant que pointeur en sablier.|  
|[CCmdTarget::DoOleVerb](../Topic/CCmdTarget::DoOleVerb.md)|Provoque une action spécifiée par un verbe OLE à exécuter.|  
|[CCmdTarget::EnableAutomation](../Topic/CCmdTarget::EnableAutomation.md)|Permet OLE automation pour l'objet d' `CCmdTarget` .|  
|[CCmdTarget::EnableConnections](../Topic/CCmdTarget::EnableConnections.md)|Active le déclenchement d'événements sur les points de connexion.|  
|[CCmdTarget::EnableTypeLib](../Topic/CCmdTarget::EnableTypeLib.md)|Active la bibliothèque de types d'un objet.|  
|[CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md)|Retourne le curseur précédent.|  
|[CCmdTarget::EnumOleVerbs](../Topic/CCmdTarget::EnumOleVerbs.md)|Énumère les verbes OLE d'un objet.|  
|[CCmdTarget::FromIDispatch](../Topic/CCmdTarget::FromIDispatch.md)|Retourne un pointeur vers l'objet d' `CCmdTarget` associé au pointeur d' `IDispatch` .|  
|[CCmdTarget::GetDispatchIID](../Topic/CCmdTarget::GetDispatchIID.md)|Obtient l'ID primaire d'interface de dispatch|  
|[CCmdTarget::GetIDispatch](../Topic/CCmdTarget::GetIDispatch.md)|Retourne un pointeur vers l'objet d' `IDispatch` associé à l'objet d' `CCmdTarget` .|  
|[CCmdTarget::GetTypeInfoCount](../Topic/CCmdTarget::GetTypeInfoCount.md)|Récupère le nombre d'interfaces des informations de type d'un objet fournit.|  
|[CCmdTarget::GetTypeInfoOfGuid](../Topic/CCmdTarget::GetTypeInfoOfGuid.md)|Récupère la description de type qui correspond au GUID spécifié.|  
|[CCmdTarget::GetTypeLib](../Topic/CCmdTarget::GetTypeLib.md)|Obtient un pointeur vers une bibliothèque de types.|  
|[CCmdTarget::GetTypeLibCache](../Topic/CCmdTarget::GetTypeLibCache.md)|Obtient le cache de bibliothèque de types.|  
|[CCmdTarget::IsInvokeAllowed](../Topic/CCmdTarget::IsInvokeAllowed.md)|Active l'appel de méthode automation.|  
|[CCmdTarget::IsResultExpected](../Topic/CCmdTarget::IsResultExpected.md)|Retourne une valeur différente de zéro si une fonction d'automation retourne une valeur.|  
|[CCmdTarget::OnCmdMsg](../Topic/CCmdTarget::OnCmdMsg.md)|Les itinéraires et les expéditions commande identities des messages.|  
|[CCmdTarget::OnFinalRelease](../Topic/CCmdTarget::OnFinalRelease.md)|Nettoie une fois OLE référence de la dernière soit libéré.|  
|[CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md)|Restaure le pointeur en sablier.|  
  
## Notes  
 Une table des messages route des commandes ou des messages aux fonctions membres que vous écrivez pour les gérer.  \(La commande d'Un est un message d'un élément de menu, d'un bouton de commande, ou d'une touche accélérateur.\)  
  
 Les principales classes d'infrastructure dérivées d' `CCmdTarget` incluent [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md), et [CFrameWnd](../../mfc/reference/cframewnd-class.md).  Si vous avez l'intention d'une nouvelle classe de gérer des messages, dérivez la classe de l'une de ces `CCmdTarget`\- classes dérivées.  Vous dériverez rarement une classe d' `CCmdTarget` directement.  
  
 Pour une vue d'ensemble des cibles de la commande et de l' `OnCmdMsg` le routage, consultez [Cible de la commande](../../mfc/command-targets.md), [Routage de commandes](../../mfc/command-routing.md), et le [messages de mappage](../../mfc/mapping-messages.md).  
  
 `CCmdTarget` inclut les fonctions membres qui gèrent l'affichage d'un pointeur en sablier.  Affichez le pointeur en sablier lorsque vous attendez une commande de prendre un intervalle de temps apparent pour exécuter.  
  
 Les tables de dispatch, semblables aux tables des messages, sont utilisées pour exposer OLE fonctionnalité d' `IDispatch` automation.  En exposant cette interface, d'autres applications \(telles que Visual Basic\) peuvent appeler dans votre application.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [exemple MFC ACDUAL](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CCmdUI Class](../../mfc/reference/ccmdui-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [COleDispatchDriver Class](../../mfc/reference/coledispatchdriver-class.md)