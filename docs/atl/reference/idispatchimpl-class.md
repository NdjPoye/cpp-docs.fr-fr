---
title: "IDispatchImpl Class | Microsoft Docs"
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
  - "IDispatchImpl"
  - "ATL.IDispatchImpl"
  - "ATL::IDispatchImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces doubles, classes"
  - "prise en charge de la classe IDispatch dans ATL"
  - "classe IDispatchImpl"
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDispatchImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation par défaut de la partie d' `IDispatch` d'une interface double.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
template<  
   class T,  
   const IID* piid= &__uuidof(T),  
   const GUID* plibid = &CAtlModule::m_libid,  
   WORD wMajor = 1,  
   WORD wMinor = 0,  
   class tihclass = CComTypeInfoHolder   
>   
class ATL_NO_VTABLE IDispatchImpl :  
   public T  
```  
  
#### Paramètres  
 \[in\] `T`  
 Une interface double.  
  
 \[in\] `piid`  
 Pointeur vers l'IID d' `T`.  
  
 \[in\] `plibid`  
 Pointeur vers le LIBID de la bibliothèque de types qui contient des informations sur l'interface.  Par défaut, la bibliothèque de types au niveau de le serveur est passée.  
  
 \[in\] `wMajor`  
 Version principale de la bibliothèque de types.  Par défaut, la valeur est 1.  
  
 \[in\] `wMinor`  
 Version secondaire de la bibliothèque de types.  Par défaut, la valeur est 0.  
  
 \[in\] `tihclass`  
 La classe utilisée pour gérer les informations de type pour `T`.  Par défaut, la valeur est `CComTypeInfoHolder`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[IDispatchImpl::IDispatchImpl](../Topic/IDispatchImpl::IDispatchImpl.md)|Constructeur.  Appelle `AddRef` sur la variable membre protégée qui gère les informations de type pour l'interface double.  Le destructeur appelle `Release`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](../Topic/IDispatchImpl::GetIDsOfNames.md)|Mappe un jeu de noms avec un jeu correspondant d'identificateurs de dispatch.|  
|[IDispatchImpl::GetTypeInfo](../Topic/IDispatchImpl::GetTypeInfo.md)|Extrait les informations de type pour l'interface double.|  
|[IDispatchImpl::GetTypeInfoCount](../Topic/IDispatchImpl::GetTypeInfoCount.md)|Détermine s'il existe des informations de type disponibles pour l'interface double.|  
|[IDispatchImpl::Invoke](../Topic/IDispatchImpl::Invoke.md)|Permet d'accéder aux méthodes et aux propriétés exposées par l'interface double.|  
  
## Notes  
 `IDispatchImpl` fournit une implémentation par défaut de la partie d' `IDispatch` de toute interface double dans un objet.  Une interface double dérive d' `IDispatch` et utilise uniquement des types compatibles automation.  Comme une dispinterface, une interface double prend en charge la liaison anticipée et la liaison tardive ; toutefois, une interface double prend également en charge la liaison vtable.  
  
 L'exemple de code suivant illustre une implémentation standard de `IDispatchImpl`.  
  
 [!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/CPP/idispatchimpl-class_1.h)]  
  
 Par défaut, recherche de classe d' `IDispatchImpl` les informations de type pour `T` dans le Registre.  Pour implémenter une interface non enregistrée, vous pouvez utiliser la classe d' `IDispatchImpl` sans accéder au Registre à l'aide d'un numéro de version intégré.  Si vous créez un objet d' `IDispatchImpl` qui a 0xFFFF comme valeur pour `wMajor` et 0xFFFF comme valeur pour `wMinor`, la classe d' `IDispatchImpl` récupère la bibliothèque de types du fichier .DLL au lieu du Registre.  
  
 `IDispatchImpl` contient un membre statique du type `CComTypeInfoHolder` qui gère les informations de type pour l'interface double.  Si vous avez plusieurs objets qui implémentent la même interface double, une seule instance d' `CComTypeInfoHolder` est utilisée.  
  
## Hiérarchie d'héritage  
 `T`  
  
 `IDispatchImpl`  
  
## Configuration requise  
 **en\-tête :** atlcom.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)