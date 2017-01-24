---
title: "CWndClassInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWndClassInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWndClassInfo class"
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWndClassInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour stocker les informations relatives à une classe de fenêtre.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CWndClassInfo  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|||  
|-|-|  
|[Inscrire](../Topic/CWndClassInfo::Register.md)|Stocke la classe de fenêtre.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_atom](../Topic/CWndClassInfo::m_atom.md)|Identifie la classe de fenêtre stockée.|  
|[m\_bSystemCursor](../Topic/CWndClassInfo::m_bSystemCursor.md)|Spécifie si la ressource curseur fait référence à un curseur du système ou un curseur contenu dans une ressource de module.|  
|[m\_lpszCursorID](../Topic/CWndClassInfo::m_lpszCursorID.md)|Spécifie le nom de la ressource curseur.|  
|[m\_lpszOrigName](../Topic/CWndClassInfo::m_lpszOrigName.md)|Contient le nom d'une classe de fenêtre existante.|  
|[m\_szAutoName](../Topic/CWndClassInfo::m_szAutoName.md)|Contient un nom ATL à partir de la classe de fenêtre.|  
|[m\_wc](../Topic/CWndClassInfo::m_wc.md)|Met à jour les informations de classe de fenêtre dans une structure de **WNDCLASSEX** .|  
|[pWndProc](../Topic/CWndClassInfo::pWndProc.md)|Points à la procédure de fenêtre d'une classe de fenêtre existante.|  
  
## Notes  
 `CWndClassInfo` gère les informations d'une classe de fenêtre.  Vous utilisez généralement `CWndClassInfo` via un de trois macros, `DECLARE_WND_CLASS`, `DECLARE_WND_CLASS_EX`, ou `DECLARE_WND_SUPERCLASS`, comme décrit dans le tableau suivant :  
  
|Macro|Description|  
|-----------|-----------------|  
|[DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md)|Les informations de registres d'`CWndClassInfo` pour une nouvelle classe de fenêtre.|  
|[DECLARE\_WND\_CLASS\_EX](../Topic/DECLARE_WND_CLASS_EX.md)|Les informations de registres d'`CWndClassInfo` pour une nouvelle classe de fenêtre, notamment les paramètres de classe.|  
|[DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md)|Les informations de registres d'`CWndClassInfo` pour une classe de fenêtre qui est basé sur une classe existante mais utilise une procédure de fenêtre différente.  Cette technique est appelée superclassing.|  
  
 Par défaut, [CWindowImpl](../../atl/reference/cwindowimpl-class.md) inclut la macro d' `DECLARE_WND_CLASS` pour créer une fenêtre selon une nouvelle classe de fenêtre.  DECLARE\_WND\_CLASS fournit des styles par défaut et la couleur d'arrière\-plan du contrôle.  Si vous souhaitez spécifier le style et la couleur d'arrière\-plan vous\-même, dérivez votre classe d' `CWindowImpl` et incluez la macro d' `DECLARE_WND_CLASS_EX` dans la définition de classe.  
  
 Si vous souhaitez créer une fenêtre selon une classe de fenêtre existante, dérivez votre classe d' `CWindowImpl` et incluez la macro d' `DECLARE_WND_SUPERCLASS` dans la définition de classe.  Par exemple :  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/CPP/cwndclassinfo-class_1.h)]  
  
 Pour plus d'informations sur les classes de fenêtres, consultez [classes de fenêtres](http://msdn.microsoft.com/library/windows/desktop/ms632596) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur l'utilisation des fenêtres dans ATL, consultez l'article [Classes de fenêtres ATL](../../atl/atl-window-classes.md).  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)