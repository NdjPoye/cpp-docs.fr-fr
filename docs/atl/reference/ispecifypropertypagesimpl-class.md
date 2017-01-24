---
title: "ISpecifyPropertyPagesImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ISpecifyPropertyPagesImpl"
  - "ATL.ISpecifyPropertyPagesImpl<T>"
  - "ATL::ISpecifyPropertyPagesImpl"
  - "ATL::ISpecifyPropertyPagesImpl<T>"
  - "ATL.ISpecifyPropertyPagesImpl"
  - "ISpecifyPropertyPagesImpl Class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISpecifyPropertyPages"
  - "ISpecifyPropertyPagesImpl class"
  - "pages de propriétés, CLSIDs associated with"
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ISpecifyPropertyPagesImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et fournit une implémentation par défaut de l'interface d' [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl :  
public ISpecifyPropertyPages  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `ISpecifyPropertyPagesImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](../Topic/ISpecifyPropertyPagesImpl::GetPages.md)|Remplit compté tableau de valeurs d'UUID.  Chaque UUID correspond à le CLSID pour l'une des pages de propriétés qui peuvent être affichées dans la feuille de propriétés de l'objet.|  
  
## Notes  
 L'interface d' [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) permet à un client pour obtenir une liste des CLSID pour les pages de propriétés prises en charge par un objet.  La classe `ISpecifyPropertyPagesImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
> [!NOTE]
>  N'exposez pas l'interface d' **ISpecifyPropertyPages** si votre objet ne prend pas en charge les pages de propriétés.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [IPropertyPageImpl Class](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl Class](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)