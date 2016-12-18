---
title: "CWinTraitsOR Class | Microsoft Docs"
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
  - "ATL.CWinTraitsOR"
  - "ATL::CWinTraitsOR"
  - "CWinTraitsOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinTraitsOR class"
  - "window styles, default values for ATL"
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinTraitsOR Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit une méthode pour standardiser les styles utilisés en créant un objet window.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
DWORD t_dwStyle= 0,  
DWORDt_dwExStyle= 0,  
class TWinTraits = CControlWinTraits   
>  
class CWinTraitsOR  
```  
  
#### Paramètres  
 `t_dwStyle`  
 Styles de fenêtre par défaut.  
  
 `t_dwExStyle`  
 Styles de fenêtre étendus par défaut.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](../Topic/CWinTraitsOR::GetWndExStyle.md)|Récupère les styles étendus pour l'objet d' `CWinTraitsOR` .|  
|[CWinTraitsOR::GetWndStyle](../Topic/CWinTraitsOR::GetWndStyle.md)|Récupère les styles standard pour l'objet d' `CWinTraitsOR` .|  
  
## Notes  
 Cette classe de [traits de fenêtre](../../atl/understanding-window-traits.md) fournit une méthode simple pour standardiser les styles utilisés pour la création d'un objet window ATL.  Utilisez une spécialisation de cette classe en tant que paramètre de modèle à [CWindowImpl](../../atl/reference/cwindowimpl-class.md) ou les autres classes de fenêtres ATL pour spécifier l'ensemble minimum de styles standard et élargi à utiliser pour les instances de cette classe de fenêtre.  
  
 Utilisez une spécialisation de ce modèle si vous souhaitez vous assurer que certains styles sont définis pour toutes les instances de la classe de fenêtre tout en laissant d'autres styles d'être définis pour chaque instance dans l'appel à [CWindowImpl::Create](../Topic/CWindowImpl::Create.md).  
  
 Si vous souhaitez fournir des styles de fenêtre par défaut qui seront utilisés uniquement lorsque aucun autre style n'est spécifiée dans l'appel à `CWindowImpl::Create`, utilisez [CWinTraits](../../atl/reference/cwintraits-class.md) à la place.  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Understanding Window Traits](../../atl/understanding-window-traits.md)