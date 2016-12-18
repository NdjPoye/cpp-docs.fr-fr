---
title: "CWinTraits Class | Microsoft Docs"
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
  - "CWinTraits"
  - "CMDIChildWinTraits"
  - "ATL.CWinTraits"
  - "CFrameWinTraits"
  - "ATL::CWinTraits"
  - "CControlWinTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlWinTraits class"
  - "CFrameWinTraits class"
  - "CMDIChildWinTraits class"
  - "CWinTraits class"
  - "window styles, default values for ATL"
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit une méthode pour standardiser les styles utilisés en créant un objet window.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
DWORD t_dwStyle= 0,  
DWORD t_dwExStyle= 0  
>  
class CWinTraits  
```  
  
#### Paramètres  
 `t_dwStyle`  
 Est la valeur par défaut les styles de fenêtre standard.  
  
 `t_dwExStyle`  
 Styles de fenêtre étendus par défaut.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinTraits::GetWndExStyle](../Topic/CWinTraits::GetWndExStyle.md)|\(Statique\) récupère les styles étendus pour l'objet d' `CWinTraits` .|  
|[CWinTraits::GetWndStyle](../Topic/CWinTraits::GetWndStyle.md)|\(Statique\) récupère les styles standard pour l'objet d' `CWinTraits` .|  
  
## Notes  
 Cette classe de [traits de fenêtre](../../atl/understanding-window-traits.md) fournit une méthode simple pour standardiser les styles utilisés pour la création d'un objet window ATL.  Utilisez une spécialisation de cette classe en tant que paramètre de modèle à [CWindowImpl](../../atl/reference/cwindowimpl-class.md) ou les autres classes de fenêtres ATL pour spécifier les styles standard et étendus par défaut utilisés pour les instances de cette classe de fenêtre.  
  
 Utilisez ce modèle lorsque vous souhaitez fournir des styles de fenêtre par défaut qui seront utilisés uniquement lorsque aucun autre style n'est spécifiée dans l'appel à [CWindowImpl::Create](../Topic/CWindowImpl::Create.md).  
  
 ATL fournit trois spécialisations prédéfinies de ce modèle pour les combinaisons courantes des styles de fenêtre :  
  
 `CControlWinTraits`  
 Conçu pour une fenêtre de contrôle standard.  Les styles standard suivants sont utilisés : **WS\_CHILD**, **WS\_VISIBLE**, **WS\_CLIPCHILDREN**, et **WS\_CLIPSIBLINGS**.  Il n'existe aucun style étendu.  
  
 `CFrameWinTraits`  
 Conçu pour une fenêtre frame standard.  Les styles utilisés standard incluent : **WS\_OVERLAPPEDWINDOW**, **WS\_CLIPCHILDREN**, et **WS\_CLIPSIBLINGS**.  Les styles étendus utilisés sont les suivantes : **WS\_EX\_APPWINDOW** et **WS\_EX\_WINDOWEDGE**.  
  
 `CMDIChildWinTraits`  
 Conçu pour une fenêtre enfant MDI standard.  Les styles utilisés standard incluent : **WS\_OVERLAPPEDWINDOW**, **WS\_CHILD**, **WS\_VISIBLE**, **WS\_CLIPCHILDREN**, et **WS\_CLIPSIBLINGS**.  Les styles étendus utilisés sont les suivantes : **WS\_EX\_MDICHILD**.  
  
 Si vous souhaitez vous assurer que certains styles sont définis pour toutes les instances de la classe de fenêtre tout en laissant d'autres styles d'être définis pour chaque instance, utilisez [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) à la place.  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [Class Members](http://msdn.microsoft.com/fr-fr/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Understanding Window Traits](../../atl/understanding-window-traits.md)