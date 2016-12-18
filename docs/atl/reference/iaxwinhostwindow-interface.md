---
title: "IAxWinHostWindow Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAxWinHostWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinHostWindow interface"
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
caps.latest.revision: 21
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinHostWindow Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette interface fournit des méthodes pour manipuler un contrôle et son objet hôte.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
interface IAxWinHostWindow : IUnknown  
  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AttachControl](../Topic/IAxWinHostWindow::AttachControl.md)|Lie un contrôle existant à l'objet hôte.|  
|[CreateControl](../Topic/IAxWinHostWindow::CreateControl.md)|Crée un contrôle et l'attache à l'objet hôte.|  
|[CreateControlEx](../Topic/IAxWinHostWindow::CreateControlEx.md)|Crée un contrôle, le associé à l'objet hôte, et installe éventuellement un gestionnaire d'événements.|  
|[QueryControl](../Topic/IAxWinHostWindow::QueryControl.md)|Retourne un pointeur d'interface vers le contrôle hébergé.|  
|[SetExternalDispatch](../Topic/IAxWinHostWindow::SetExternalDispatch.md)|Définit l'interface externe d' `IDispatch` .|  
|[SetExternalUIHandler](../Topic/IAxWinHostWindow::SetExternalUIHandler.md)|Définit l'interface externe d' `IDocHostUIHandlerDispatch` .|  
  
## Notes  
 Cette interface est exposée par le contrôle ActiveX ATL hébergement d'objets.  Appelez les méthodes sur cette interface pour créer la liaison et\/ou un contrôle à l'objet hôte, pour obtenir une interface d'un contrôle hébergé, ou pour définir la dispinterface externe ou le gestionnaire d'interface utilisateur pour une utilisation en hébergeant le navigateur web.  
  
## Configuration requise  
 La définition de cette interface est disponible en tant que fichier IDL ou C\+\+, comme indiqué ci\-dessous.  
  
|Type de définition|Fichier|  
|------------------------|-------------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(également inclus dans ATLBase.h\)|  
  
## Voir aussi  
 [IAxWinAmbientDispatch Interface](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../Topic/CAxWindow::QueryHost.md)   
 [AtlAxGetHost](../Topic/AtlAxGetHost.md)