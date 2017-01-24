---
title: "IProvideClassInfo2Impl Class | Microsoft Docs"
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
  - "IProvideClassInfo2"
  - "ATL.IProvideClassInfo2Impl"
  - "IProvideClassInfo2Impl"
  - "ATL::IProvideClassInfo2Impl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class information, ATL"
  - "IProvideClassInfo2 ATL implementation"
  - "IProvideClassInfo2Impl class"
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IProvideClassInfo2Impl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit une implémentation par défaut des méthodes d' [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) et d' [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) .  
  
## Syntaxe  
  
```  
  
      template <  
   const CLSID* pcoclsid,  
   const IID* psrcid,  
   const GUID* plibid = &CAtlModule::m_libid,  
   WORD wMajor = 1,  
   WORD wMinor = 0,  
   class tihclass = CComTypeInfoHolder   
>  
class ATL_NO_VTABLE IProvideClassInfo2Impl :  
   public IProvideClassInfo2  
```  
  
#### Paramètres  
 *pcoclsid*  
 Pointeur vers l'identificateur les coclasses.  
  
 *psrcid*  
 Un pointeur vers l'identificateur de la dispinterface sortante par défaut des coclasses.  
  
 `plibid`  
 Pointeur vers le LIBID de la bibliothèque de types qui contient des informations sur l'interface.  Par défaut, la bibliothèque de types au niveau de le serveur est passée.  
  
 `wMajor`  
 Version principale de la bibliothèque de types.  La valeur par défaut est 1.  
  
 `wMinor`  
 Version secondaire de la bibliothèque de types.  La valeur par défaut est 0.  
  
 `tihclass`  
 La classe utilisée pour gérer les informations de type des coclasses.  La valeur par défaut est `CComTypeInfoHolder`.  
  
## Membres  
  
### Constructeurs  
  
|Nom|Description|  
|---------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](../Topic/IProvideClassInfo2Impl::IProvideClassInfo2Impl.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](../Topic/IProvideClassInfo2Impl::GetClassInfo.md)|Extrait un pointeur d' **ITypeInfo** aux informations de type des coclasses.|  
|[IProvideClassInfo2Impl::GetGUID](../Topic/IProvideClassInfo2Impl::GetGUID.md)|Récupère GUID pour la dispinterface sortante de l'objet.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[IProvideClassInfo2Impl::\_tih](../Topic/IProvideClassInfo2Impl::_tih.md)|Gère les informations de type pour la coclasse.|  
  
## Notes  
 l'interface d' [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) étend [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) en ajoutant la méthode d' `GetGUID` .  Cette méthode permet à un client pour récupérer l'interface sortante IID d'un objet pour son jeu d'événements par défaut.  La classe `IProvideClassInfo2Impl` fournit une implémentation par défaut des méthodes d' **IProvideClassInfo** et d' `IProvideClassInfo2` .  
  
 `IProvideClassInfo2Impl` contient un membre statique du type `CComTypeInfoHolder` qui gère les informations de type pour la coclasse.  
  
## Hiérarchie d'héritage  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)