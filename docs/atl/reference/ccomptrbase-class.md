---
title: "CComPtrBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComPtrBase"
  - "ATL::CComPtrBase<T>"
  - "ATL.CComPtrBase<T>"
  - "ATL::CComPtrBase"
  - "CComPtrBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComPtrBase class"
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComPtrBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe constitue une base pour les classes intelligentes de pointeur à l'aide de les routines de mémoire COM.  
  
## Syntaxe  
  
```  
  
      template <  
   class T   
> class CComPtrBase  
```  
  
#### Paramètres  
 `T`  
 Le type d'objet à référencer par le pointeur intelligent.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComPtrBase::~CComPtrBase](../Topic/CComPtrBase::~CComPtrBase.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)|Appelez cette méthode pour créer une connexion le récepteur entre le point de connexion d'`CComPtrBase` et d'un client.|  
|[CComPtrBase::Attach](../Topic/CComPtrBase::Attach.md)|Appelez cette méthode pour prendre la propriété d'un pointeur existant.|  
|[CComPtrBase::CoCreateInstance](../Topic/CComPtrBase::CoCreateInstance.md)|Appelez cette méthode pour créer un objet de la classe associée à un ID de classe spécifiée ou pour programmer l'ID|  
|[CComPtrBase::CopyTo](../Topic/CComPtrBase::CopyTo.md)|Appelez cette méthode pour copier le pointeur d' `CComPtrBase` à une autre variable pointeur.|  
|[CComPtrBase::Detach](../Topic/CComPtrBase::Detach.md)|Appelez cette méthode pour libérer la propriété d'un pointeur.|  
|[CComPtrBase::IsEqualObject](../Topic/CComPtrBase::IsEqualObject.md)|Appelez cette méthode pour vérifier si les points spécifiés d' **IUnknown** à la même objet associé à l'objet d' `CComPtrBase` .|  
|[CComPtrBase::QueryInterface](../Topic/CComPtrBase::QueryInterface.md)|Appelez cette méthode pour retourner un pointeur vers une interface spécifiée.|  
|[CComPtrBase::Release](../Topic/CComPtrBase::Release.md)|Appelez cette méthode pour libérer l'interface.|  
|[CComPtrBase::SetSite](../Topic/CComPtrBase::SetSite.md)|Appelez cette méthode pour définir le site de l'objet d' `CComPtrBase` à **IUnknown** de l'objet parent.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComPtrBase::operator T\*](../Topic/CComPtrBase::operator%20T*.md)|l'opérateur de cast.|  
|[CComPtrBase::operator \!](../Topic/CComPtrBase::operator%20!.md)|L'opérateur NOT.|  
|[CComPtrBase::operator &](../Topic/CComPtrBase::operator%20&.md)|Et opérateur.|  
|[CComPtrBase::operator \*](../Topic/CComPtrBase::operator%20*.md)|L'opérateur \*.|  
|[CComPtrBase::operator \<](../Topic/CComPtrBase::operator%20%3C.md)|Inférieur à l'opérateur.|  
|[CComPtrBase::operator \=\=](../Topic/CComPtrBase::operator%20==.md)|l'opérateur d'égalité.|  
|[CComPtrBase::operator \-\>](../Topic/CComPtrBase::operator%20-%3E.md)|L'opérateur de pointeurs vers membres.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComPtrBase::p](../Topic/CComPtrBase::p.md)|La variable de membre de pointeur.|  
  
## Notes  
 Cette classe constitue la base des autres pointeurs intelligents qui utilisent des routines de gestion de la mémoire COM, tels que [CComQIPtr](../../atl/reference/ccomqiptr-class.md) et [CComPtr](../../atl/reference/ccomptr-class.md).  Les classes dérivées ajouter leurs propres constructeurs et opérateurs, mais dépendent les méthodes fournies par `CComPtrBase`.  
  
## Configuration requise  
 **Header:** atlcomcli.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)