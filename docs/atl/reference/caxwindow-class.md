---
title: "CAxWindow Class | Microsoft Docs"
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
  - "CAxWindowT"
  - "CAxWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, héberger des contrôles ActiveX"
  - "CAxWindow class"
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAxWindow Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour manipuler une fenêtre hébergement d'un contrôle ActiveX.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CAxWindow : public CWindow  
  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AttachControl](../Topic/CAxWindow::AttachControl.md)|Joint un contrôle ActiveX existant à l'objet d' `CAxWindow` .|  
|[CAxWindow](../Topic/CAxWindow::CAxWindow.md)|Construit un objet `CAxWindow`.|  
|[CreateControl](../Topic/CAxWindow::CreateControl.md)|Crée un contrôle ActiveX, l'initialise, et le héberge dans la fenêtre d' `CAxWindow` .|  
|[CreateControlEx](../Topic/CAxWindow::CreateControlEx.md)|Crée un contrôle ActiveX et extrait un pointeur d'interface \(ou des pointeurs\) du contrôle.|  
|[GetWndClassName](../Topic/CAxWindow::GetWndClassName.md)|\(Statique\) extrait le nom de classe intégré de l'objet d' `CAxWindow` .|  
|[QueryControl](../Topic/CAxWindow::QueryControl.md)|Récupère **IUnknown** du contrôle ActiveX hébergé.|  
|[QueryHost](../Topic/CAxWindow::QueryHost.md)|Récupère le pointeur d' **IUnknown** de l'objet d' `CAxWindow` .|  
|[SetExternalDispatch](../Topic/CAxWindow::SetExternalDispatch.md)|Définit l'interface de dispatch externe utilisée par l'objet d' `CAxWindow` .|  
|[SetExternalUIHandler](../Topic/CAxWindow::SetExternalUIHandler.md)|Définit l'interface externe d' **IDocHostUIHandler** utilisée par l'objet d' `CAxWindow` .|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/CAxWindow::operator%20=.md)|Assigne **HWND** à un objet existant de**CAxWindow** .|  
  
## Notes  
 Cette classe fournit des méthodes pour manipuler une fenêtre qui héberge un contrôle ActiveX.  l'hébergement est fourni par « **AtlAxWin80"**, qui est encapsulé par `CAxWindow`.  
  
 La classe `CAxWindow` est implémentée comme une spécialisation de la classe d' `CAxWindowT` .  Cette spécialisation est déclarée comme suit :  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 Si vous devez modifier la classe de base, vous pouvez utiliser `CAxWindowT` et spécifier la classe de base comme argument template.  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [Exemple d'ATLCON](../../top/visual-cpp-samples.md)   
 [CWindow Class](../../atl/reference/cwindow-class.md)   
 [Notions de base des contrôles composites](../../atl/atl-composite-control-fundamentals.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [FAQ sur la relation contenant\-contenu des contrôles](../../atl/atl-control-containment-faq.md)