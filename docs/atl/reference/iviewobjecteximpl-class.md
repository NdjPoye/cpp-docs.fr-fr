---
title: "IViewObjectExImpl Class | Microsoft Docs"
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
  - "ATL::IViewObjectExImpl<T>"
  - "ATL.IViewObjectExImpl"
  - "ATL::IViewObjectExImpl"
  - "ATL.IViewObjectExImpl<T>"
  - "IViewObjectExImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), drawing"
  - "advise sinks"
  - "IViewObjectEx ATL implementation"
  - "IViewObjectExImpl class"
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IViewObjectExImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et fournit des implémentations par défaut des interfaces d' [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), d' [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), et d' [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IViewObjectExImpl :  
public IViewObjectEx  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IViewObjectExImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IViewObjectExImpl::Draw](../Topic/IViewObjectExImpl::Draw.md)|Dessine une représentation du contrôle dans un contexte de périphérique.|  
|[IViewObjectExImpl::Freeze](../Topic/IViewObjectExImpl::Freeze.md)|Gèle la représentation effectuée d'un contrôle afin qu'il ne change pas avant `Unfreeze`.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IViewObjectExImpl::GetAdvise](../Topic/IViewObjectExImpl::GetAdvise.md)|Extrait une connexion existante de récepteur de notifications sur le contrôle, le cas échéant.|  
|[IViewObjectExImpl::GetColorSet](../Topic/IViewObjectExImpl::GetColorSet.md)|Retourne la palette logique utilisée par le contrôle pour le dessin.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IViewObjectExImpl::GetExtent](../Topic/IViewObjectExImpl::GetExtent.md)|Extrait la taille d'affichage du contrôle en unités HIMETRIC \(0,01 millimètres par unité\) de la donnée membre de classe de contrôle [CComControlBase::m\_sizeExtent](../Topic/CComControlBase::m_sizeExtent.md).|  
|[IViewObjectExImpl::GetNaturalExtent](../Topic/IViewObjectExImpl::GetNaturalExtent.md)|Fournit des indications de dimensionnement du conteneur de cet objet à utiliser comme l'utilisateur redimensionne la.|  
|[IViewObjectExImpl::GetRect](../Topic/IViewObjectExImpl::GetRect.md)|Retourne un rectangle qui décrivent un aspect de dessin demandé.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IViewObjectExImpl::GetViewStatus](../Topic/IViewObjectExImpl::GetViewStatus.md)|Informations de retour sur l'opacité de l'objet et les aspects de dessin sont pris en charge.|  
|[IViewObjectExImpl::QueryHitPoint](../Topic/IViewObjectExImpl::QueryHitPoint.md)|Contrôle si le point spécifié dans le rectangle spécifié et retourne une valeur de [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) dans `pHitResult`.|  
|[IViewObjectExImpl::QueryHitRect](../Topic/IViewObjectExImpl::QueryHitRect.md)|Vérifie si le rectangle de l'affichage du contrôle se superpose tout point dans le rectangle spécifié d'emplacement et retourne une valeur de **HITRESULT** dans `pHitResult`.|  
|[IViewObjectExImpl::SetAdvise](../Topic/IViewObjectExImpl::SetAdvise.md)|Installation via une connexion entre le contrôle et un récepteur de notifications par conséquent il peut annoncer le récepteur sur les modifications de la vue du contrôle.|  
|[IViewObjectExImpl::Unfreeze](../Topic/IViewObjectExImpl::Unfreeze.md)|Dégèle la représentation effectuée du contrôle.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
  
## Notes  
 Les interfaces d' [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), d' [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), et d' [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) permettent à un contrôle d'afficher directement, et de créer et gérer un récepteur de notifications pour informer le conteneur de modifications dans l'affichage.  L'interface d' **IViewObjectEx** fournit la prise en charge des fonctionnalités de contrôle étendues telles que le dessin sans scintillement, les contrôles non rectangulaires et transparent, et le test d'atteinte \(par exemple, déterminent l'espacement un clic de souris doit être considérée sur le contrôle.\)  La classe `IViewObjectExImpl` fournit une implémentation par défaut de ces interfaces et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
## Hiérarchie d'héritage  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Didacticiel](../../atl/active-template-library-atl-tutorial.md)   
 [Création d'un projet ATL](../../atl/reference/creating-an-atl-project.md)   
 [Class Overview](../../atl/atl-class-overview.md)