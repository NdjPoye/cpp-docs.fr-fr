---
title: "CComDynamicUnkArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComDynamicUnkArray"
  - "CComDynamicUnkArray"
  - "ATL::CComDynamicUnkArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComDynamicUnkArray class"
  - "points de connexion (C++), gérer"
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CComDynamicUnkArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe stocke un tableau de pointeurs d' **IUnknown** .  
  
## Syntaxe  
  
```  
class CComDynamicUnkArray  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](../Topic/CComDynamicUnkArray::CComDynamicUnkArray.md)|Constructeur.  Initialise les valeurs de collection à **NULL** et la taille de collection à zéro.|  
|[CComDynamicUnkArray::~CComDynamicUnkArray](../Topic/CComDynamicUnkArray::~CComDynamicUnkArray.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComDynamicUnkArray::Add](../Topic/CComDynamicUnkArray::Add.md)|Appelez cette méthode pour ajouter un pointeur d' `IUnknown` au tableau.|  
|[CComDynamicUnkArray::begin](../Topic/CComDynamicUnkArray::begin.md)|Retourne un pointeur vers le premier pointeur d' `IUnknown` dans la collection.|  
|[CComDynamicUnkArray::clear](../Topic/CComDynamicUnkArray::clear.md)|Vide tableau.|  
|[CComDynamicUnkArray::end](../Topic/CComDynamicUnkArray::end.md)|Retourne un pointeur vers un au delà de le dernier pointeur d' **IUnknown** dans la collection.|  
|[CComDynamicUnkArray::GetAt](../Topic/CComDynamicUnkArray::GetAt.md)|Récupère l'élément au niveau de l'index spécifié.|  
|[CComDynamicUnkArray::GetCookie](../Topic/CComDynamicUnkArray::GetCookie.md)|Appelez cette méthode pour obtenir le cookie associé à un pointeur donnée d' **IUnknown** .|  
|[CComDynamicUnkArray::GetSize](../Topic/CComDynamicUnkArray::GetSize.md)|Retourne la longueur d'un tableau.|  
|[CComDynamicUnkArray::GetUnknown](../Topic/CComDynamicUnkArray::GetUnknown.md)|Appelez cette méthode pour obtenir le pointeur d' **IUnknown** associé à un cookie donné.|  
|[CComDynamicUnkArray::Remove](../Topic/CComDynamicUnkArray::Remove.md)|Appelez cette méthode pour supprimer un pointeur d' **IUnknown** du tableau.|  
  
## Notes  
 **CComDynamicUnkArray** contient un tableau dynamique allouée de pointeurs d' **IUnknown** , chaque une interface d'un point de connexion.  **CComDynamicUnkArray** peut être utilisé comme paramètre à la classe de modèle d' [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) .  
  
 Les méthodes [démarrez](../Topic/CComDynamicUnkArray::begin.md) et [fin](../Topic/CComDynamicUnkArray::end.md) de **CComDynamicUnkArray** peuvent être utilisées pour parcourir tous les points de connexion \(par exemple, lorsqu'un événement est déclenché\).  
  
 Consultez l' [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md) pour plus d'informations sur automatiser la création des proxies de point de connexion.  
  
> [!NOTE]
>  **Note** la classe **CComDynamicUnkArray** est utilisé par l'assistant **Add Class** en créant un contrôle qui a des points de connexion.  Si vous voulez spécifier le nombre de points de connexion manuellement, modifiez la référence de **CComDynamicUnkArray** à `CComUnkArray<``>`*n* , où *n* est le nombre de points de connexion nécessaires.  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComUnkArray Class](../../atl/reference/ccomunkarray-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)