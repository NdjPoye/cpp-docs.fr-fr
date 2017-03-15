---
title: "_U_STRINGorID Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL._U_STRINGorID"
  - "ATL::_U_STRINGorID"
  - "_U_STRINGorID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_STRINGorID class"
  - "U_STRINGorID class"
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# _U_STRINGorID Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe d'adaptateur d'argument permet des noms de ressources \(`LPCTSTR`s\) ou des identificateurs de ressource \(**uint**s\) à passer à une fonction sans que l'appelant de convertir l'ID d'une chaîne à l'aide de la macro de **MAKEINTRESOURCE** .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class _U_STRINGorID  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[\_U\_STRINGorID::\_U\_STRINGorID](../Topic/_U_STRINGorID::_U_STRINGorID.md)|Constructeur.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[\_U\_STRINGorID::m\_lpstr](../Topic/_U_STRINGorID::m_lpstr.md)|L'identificateur de ressource.|  
  
## Notes  
 Cette classe est conçue pour implémenter des wrappers à l'API de gestion des ressources windows comme les fonctions de [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042), de [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), et de [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990) , qui acceptent un argument d' `LPCTSTR` qui peut être le nom d'une ressource ou son ID.  
  
 La classe définit deux surcharges de constructeur : il reçoit un argument d' `LPCTSTR` et l'autre reçoit un argument de **uint** .  L'argument de **uint** est converti en un type de ressource avec les fonctions de gestion des ressources windows à l'aide de la macro de **MAKEINTRESOURCE** et le résultat stockés dans le membre unique de la classe, [m\_lpstr](../Topic/_U_STRINGorID::m_lpstr.md).  L'argument au constructeur d' `LPCTSTR` est stocké directement sans conversion.  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)