---
title: "_U_MENUorID Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL._U_MENUorID"
  - "ATL::_U_MENUorID"
  - "_U_MENUorID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_MENUorID class"
  - "U_MENUorID class"
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# _U_MENUorID Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des wrappers pour **CreateWindow** et **CreateWindowEx**.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class _U_MENUorID  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[\_U\_MENUorID::\_U\_MENUorID](../Topic/_U_MENUorID::_U_MENUorID.md)|Constructeur.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[\_U\_MENUorID::m\_hMenu](../Topic/_U_MENUorID::m_hMenu.md)|Un handle d'un menu.|  
  
## Notes  
 Cette classe d'adaptateur d'argument autorise les identificateurs \(**uint**s\) ou les handles de menu \(`HMENU`s\) à passer à une fonction sans nécessiter un cast explicite sur la partie de l'appelant.  
  
 Cette classe est conçue pour implémenter des wrappers aux fonctions API Windows, en particulier de [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) et de [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) , qui acceptent un argument d' `HMENU` qui peut être un identificateur de fenêtre enfant \(**uint**\) plutôt qu'un handle de menu.  Par exemple, vous pouvez consulter cette classe de service comme paramètre à [CWindowImpl::Create](../Topic/CWindowImpl::Create.md).  
  
 La classe définit deux surcharges de constructeur : il reçoit un argument de **uint** et l'autre accepte un argument d' `HMENU` .  L'argument de **uint** est simplement casté à `HMENU` dans le constructeur et le résultat stockés dans le membre unique de la classe, [m\_hMenu](../Topic/_U_MENUorID::m_hMenu.md).  L'argument au constructeur d' `HMENU` est stocké directement sans conversion.  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)