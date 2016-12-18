---
title: "IPropertyPageImpl Class | Microsoft Docs"
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
  - "IPropertyPageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage ATL implementation"
  - "IPropertyPageImpl class"
  - "pages de propriétés"
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPropertyPageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et fournit une implémentation par défaut de l'interface d' [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template< class   
      T  
      >  
class IPropertyPageImpl  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IPropertyPageImpl`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[IPropertyPageImpl::IPropertyPageImpl](../Topic/IPropertyPageImpl::IPropertyPageImpl.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IPropertyPageImpl::Activate](../Topic/IPropertyPageImpl::Activate.md)|Crée la fenêtre boîte de dialogue de la page de propriétés.|  
|[IPropertyPageImpl::Apply](../Topic/IPropertyPageImpl::Apply.md)|S'applique aux valeurs actuelles de la page de propriétés aux objets sous\-jacents spécifiés via `SetObjects`.  L'implémentation ATL retourne `S_OK`.|  
|[IPropertyPageImpl::Deactivate](../Topic/IPropertyPageImpl::Deactivate.md)|Perd la fenêtre créée avec **Activate**.|  
|[IPropertyPageImpl::GetPageInfo](../Topic/IPropertyPageImpl::GetPageInfo.md)|Récupère des informations sur la page de propriétés.|  
|[IPropertyPageImpl::Help](../Topic/IPropertyPageImpl::Help.md)|Appelle l'aide de windows pour la page de propriétés.|  
|[IPropertyPageImpl::IsPageDirty](../Topic/IPropertyPageImpl::IsPageDirty.md)|Indique si la page de propriétés a été modifié depuis qu'elle a été activée.|  
|[IPropertyPageImpl::Move](../Topic/IPropertyPageImpl::Move.md)|Les positions et redimensionne la boîte de dialogue de page de propriétés.|  
|[IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md)|Signale l'état de la page de propriétés comme changé ou inchangé.|  
|[IPropertyPageImpl::SetObjects](../Topic/IPropertyPageImpl::SetObjects.md)|Fournit un tableau de pointeurs d' **IUnknown** pour les objets associés à la page de propriétés.  Ces objets reçoivent les valeurs actuelles de la page de propriétés via un appel à **Appliquer**.|  
|[IPropertyPageImpl::SetPageSite](../Topic/IPropertyPageImpl::SetPageSite.md)|Fournit à la page de propriétés un pointeur d' `IPropertyPageSite` , dans lequel la page de propriétés communique avec le frame de propriété.|  
|[IPropertyPageImpl::Show](../Topic/IPropertyPageImpl::Show.md)|Rend la boîte de dialogue de page de propriétés visible ou invisible.|  
|[IPropertyPageImpl::TranslateAccelerator](../Topic/IPropertyPageImpl::TranslateAccelerator.md)|Traite une séquence de touches spécifiée.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IPropertyPageImpl::m\_bDirty](../Topic/IPropertyPageImpl::m_bDirty.md)|Spécifie si l'état de la page de propriétés a changé.|  
|[IPropertyPageImpl::m\_dwDocString](../Topic/IPropertyPageImpl::m_dwDocString.md)|Stocke l'identificateur de la ressource associé à la chaîne de texte qui décrit la page de propriétés.|  
|[IPropertyPageImpl::m\_dwHelpContext](../Topic/IPropertyPageImpl::m_dwHelpContext.md)|Stocke l'identificateur de contexte pour la rubrique d'aide associée à la page de propriétés.|  
|[IPropertyPageImpl::m\_dwHelpFile](../Topic/IPropertyPageImpl::m_dwHelpFile.md)|Stocke l'identificateur de ressource associé au nom du fichier d'aide décrivant la page de propriétés.|  
|[IPropertyPageImpl::m\_dwTitle](../Topic/IPropertyPageImpl::m_dwTitle.md)|Stocke l'identificateur de la ressource associé à la chaîne de texte qui s'affiche dans l'onglet de la page de propriétés.|  
|[IPropertyPageImpl::m\_nObjects](../Topic/IPropertyPageImpl::m_nObjects.md)|Stocke le nombre d'objets associés à la page de propriétés.|  
|[IPropertyPageImpl::m\_pPageSite](../Topic/IPropertyPageImpl::m_pPageSite.md)|Pointe vers l'interface d' `IPropertyPageSite` via laquelle la page de propriétés communique avec le frame de propriété.|  
|[IPropertyPageImpl::m\_ppUnk](../Topic/IPropertyPageImpl::m_ppUnk.md)|Pointe vers un tableau de pointeurs d' **IUnknown** aux objets associés à la page de propriétés.|  
|[IPropertyPageImpl::m\_size](../Topic/IPropertyPageImpl::m_size.md)|Stocke la hauteur et la largeur de la boîte de dialogue de la page de propriétés, en pixels.|  
  
## Notes  
 l'interface d' [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) permet à un objet pour gérer une page de propriétés particulière dans une feuille de propriétés.  La classe `IPropertyPageImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IPropertyPage`  
  
 `IPropertyPageImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [IPropertyPage2Impl Class](../../atl/reference/ipropertypage2impl-class.md)   
 [IPerPropertyBrowsingImpl Class](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl Class](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)