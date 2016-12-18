---
title: "CComUnkArray Class | Microsoft Docs"
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
  - "ATL.CComUnkArray"
  - "ATL.CComUnkArray<nMaxSize>"
  - "ATL::CComUnkArray<nMaxSize>"
  - "ATL::CComUnkArray"
  - "CComUnkArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComUnkArray class"
  - "points de connexion (C++), gérer"
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComUnkArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe stocke des pointeurs d' **IUnknown** , et est conçue pour être utilisée comme paramètre à la classe de modèle d' [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) .  
  
## Syntaxe  
  
```  
template<  
   unsigned int nMaxSize  
>  
class CComUnkArray  
```  
  
#### Paramètres  
 *nMaxSize*  
 Le nombre maximal de pointeurs d' **IUnknown** qui peuvent être conservés dans le tableau statique.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComUnkArray::CComUnkArray](../Topic/CComUnkArray::CComUnkArray.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComUnkArray::Add](../Topic/CComUnkArray::Add.md)|Appelez cette méthode pour ajouter un pointeur d' **IUnknown** au tableau.|  
|[CComUnkArray::begin](../Topic/CComUnkArray::begin.md)|Retourne un pointeur vers le premier pointeur d' **IUnknown** dans la collection.|  
|[CComUnkArray::end](../Topic/CComUnkArray::end.md)|Retourne un pointeur vers un au delà de le dernier pointeur d' **IUnknown** dans la collection.|  
|[CComUnkArray::GetCookie](../Topic/CComUnkArray::GetCookie.md)|Appelez cette méthode pour obtenir le cookie associé à un pointeur donnée d' **IUnknown** .|  
|[CComUnkArray::GetUnknown](../Topic/CComUnkArray::GetUnknown.md)|Appelez cette méthode pour obtenir le pointeur d' **IUnknown** associé à un cookie donné.|  
|[CComUnkArray::Remove](../Topic/CComUnkArray::Remove.md)|Appelez cette méthode pour supprimer un pointeur d' **IUnknown** du tableau.|  
  
## Notes  
 **CComUnkArray** contient un nombre fixe de pointeurs d' **IUnknown** , chaque une interface d'un point de connexion.  **CComUnkArray** peut être utilisé comme paramètre à la classe de modèle d' [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) .  **CComUnkArray\<1\>** est une spécialisation de modèle de **CComUnkArray** qui a été optimisée pour un point de connexion.  
  
 Les méthodes [démarrez](../Topic/CComUnkArray::begin.md) et [fin](../Topic/CComUnkArray::end.md) de **CComUnkArray** peuvent être utilisées pour parcourir tous les points de connexion \(par exemple, lorsqu'un événement est déclenché\).  
  
 Consultez l' [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md) pour plus d'informations sur automatiser la création des proxies de point de connexion.  
  
> [!NOTE]
>  **Note** la classe [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) est utilisé par l'assistant **Add Class** en créant un contrôle qui a des points de connexion.  Si vous voulez spécifier le nombre de points de connexion manuellement, modifiez la référence de **CComDynamicUnkArray** à `CComUnkArray<``>`*n* , où *n* est le nombre de points de connexion nécessaires.  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComDynamicUnkArray Class](../../atl/reference/ccomdynamicunkarray-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)