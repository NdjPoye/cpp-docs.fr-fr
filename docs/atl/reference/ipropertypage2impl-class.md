---
title: "IPropertyPage2Impl Class | Microsoft Docs"
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
  - "IPropertyPage2Impl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage2 ATL implementation"
  - "IPropertyPage2Impl class"
  - "pages de propriétés"
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPropertyPage2Impl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et hérite l'implémentation par défaut d' [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template< class   
      T  
      >  
class IPropertyPage2Impl : public IPropertyPageImpl< T>  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IPropertyPage2Impl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IPropertyPage2Impl::EditProperty](../Topic/IPropertyPage2Impl::EditProperty.md)|Spécifie que le contrôle de propriété recevra le focus lorsque la page de propriétés est activée.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
  
## Notes  
 l'interface d' [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) étend [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) en ajoutant la méthode d' `EditProperty` .  Cette méthode permet à un client pour sélectionner une propriété spécifique dans un objet page de propriétés.  
  
 La classe `IPropertyPage2Impl` retourne simplement **E\_NOTIMPL** pour **IPropertyPage2::EditProperty**.  Toutefois, il hérite l'implémentation par défaut d' [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 Lorsque vous créez une page de propriétés, la classe est généralement dérivée d' `IPropertyPageImpl`.  Pour fournir la prise en charge supplémentaire d' **IPropertyPage2**, modifiez la définition de classe et remplacez la méthode d' `EditProperty` .  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [IPerPropertyBrowsingImpl Class](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl Class](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)