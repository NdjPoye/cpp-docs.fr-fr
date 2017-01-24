---
title: "CComQIPtr Class | Microsoft Docs"
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
  - "ATL.CComQIPtr"
  - "ATL::CComQIPtr"
  - "CComQIPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComQIPtr class"
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComQIPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe intelligente de pointeur pour gérer des pointeurs d'interface COM.  
  
## Syntaxe  
  
```  
  
      template<  
   class T,  
   const IID* piid = &__uuidof(T)  
>  
class CComQIPtr: public CComPtr<T>  
```  
  
#### Paramètres  
 `T`  
 Une interface COM qui spécifie le type de pointeur à enregistrer.  
  
 `piid`  
 Pointeur vers l'IID d' `T`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)|Constructeur.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComQIPtr::operator \=](../Topic/CComQIPtr::operator%20=.md)|Assigne un pointeur vers un pointeur de membre.|  
  
## Notes  
 ATL utilise `CComQIPtr` et [CComPtr](../../atl/reference/ccomptr-class.md) pour gérer des pointeurs d'interface COM, qui dérivent de [CComPtrBase](../../atl/reference/ccomptrbase-class.md).  Les deux classes effectuent le décompte de références automatique par des appels à `AddRef` et à **Release**.  Les opérateurs surchargés effectuent des opérations de pointeur.  
  
## Hiérarchie d'héritage  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## Configuration requise  
 **Header:** atlcomcli.h  
  
## Voir aussi  
 [CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)   
 [CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)   
 [CComPtrBase Class](../../atl/reference/ccomptrbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits Class](../../atl/reference/ccomqiptrelementtraits-class.md)