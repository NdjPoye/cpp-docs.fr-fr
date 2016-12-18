---
title: "IPerPropertyBrowsingImpl Class | Microsoft Docs"
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
  - "ATL.IPerPropertyBrowsingImpl"
  - "IPerPropertyBrowsing"
  - "ATL::IPerPropertyBrowsingImpl"
  - "ATL::IPerPropertyBrowsingImpl<T>"
  - "IPerPropertyBrowsingImpl"
  - "ATL.IPerPropertyBrowsingImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPerPropertyBrowsing, ATL (implémentation)"
  - "IPerPropertyBrowsingImpl class"
  - "pages de propriétés, accessing information"
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPerPropertyBrowsingImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et permet à un client d'accéder aux informations dans les pages d'une propriété de l'objet.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :  
public IPerPropertyBrowsing  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IPerPropertyBrowsingImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](../Topic/IPerPropertyBrowsingImpl::GetDisplayString.md)|Extrait une chaîne décrivant une propriété donnée.|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](../Topic/IPerPropertyBrowsingImpl::GetPredefinedStrings.md)|Récupère un tableau de chaînes qui correspondent aux valeurs d'une propriété donnée peut recevoir.|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](../Topic/IPerPropertyBrowsingImpl::GetPredefinedValue.md)|Récupère **variant** contenant la valeur d'une propriété identifiée par un DISPID donné.  Le DISPID est associé au nom de chaîne extrait d' `GetPredefinedStrings`.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](../Topic/IPerPropertyBrowsingImpl::MapPropertyToPage.md)|Récupère le CLSID de la page de propriétés associée à une propriété donnée.|  
  
## Notes  
 L'interface d' [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432) permet à un client d'accéder aux informations dans les pages d'une propriété de l'objet.  La classe `IPerPropertyBrowsingImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
> [!NOTE]
>  Si vous utilisez Microsoft Access comme application conteneur, vous devez dériver votre classe d' `IPerPropertyBrowsingImpl`.  Sinon, l'accès ne chargera pas votre contrôle.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [IPropertyPageImpl Class](../../atl/reference/ipropertypageimpl-class.md)   
 [ISpecifyPropertyPagesImpl Class](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)