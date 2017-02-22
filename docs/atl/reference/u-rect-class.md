---
title: "_U_RECT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::_U_RECT"
  - "_U_RECT"
  - "ATL._U_RECT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_RECT class"
  - "U_RECT class"
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# _U_RECT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe d'adaptateur d'argument permet des pointeurs ou des références d' `RECT` à passer à une fonction qui est implémentée en termes de pointeurs.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class _U_RECT  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[\_U\_RECT::\_U\_RECT](../Topic/_U_RECT::_U_RECT.md)|Constructeur.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[\_U\_RECT::m\_lpRect](../Topic/_U_RECT::m_lpRect.md)|Pointeur vers `RECT`.|  
  
## Notes  
 La classe définit deux surcharges de constructeur : il reçoit un argument de **RECT&** et l'autre accepte un argument d' `LPRECT` .  Le premier constructeur stocke l'adresse de l'argument de référence dans le membre unique de la classe, [m\_lpRect](../Topic/_U_RECT::m_lpRect.md).  L'argument au constructeur de pointeur est stocké directement sans conversion.  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)