---
title: "IDataObjectImpl Class | Microsoft Docs"
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
  - "IDataObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "data transfer [C++]"
  - "data transfer [C++], Uniform Data Transfer"
  - "IDataObject, ATL (implémentation)"
  - "IDataObjectImpl class"
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDataObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour prendre en charge l'Uniform Data Transfer et gérer des connexions.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template< class   
      T  
      >  
class IDataObjectImpl  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IDataObjectImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IDataObjectImpl::DAdvise](../Topic/IDataObjectImpl::DAdvise.md)|Établit une connexion entre l'objet de données et un récepteur de notifications.  Cela permet au récepteur de notifications de recevoir des notifications des modifications de l'objet.|  
|[IDataObjectImpl::DUnadvise](../Topic/IDataObjectImpl::DUnadvise.md)|Termine une connexion créée précédemment dans `DAdvise`.|  
|[IDataObjectImpl::EnumDAdvise](../Topic/IDataObjectImpl::EnumDAdvise.md)|Crée un énumérateur pour itérer au sein des connexions de notifications actuelles.|  
|[IDataObjectImpl::EnumFormatEtc](../Topic/IDataObjectImpl::EnumFormatEtc.md)|Crée un énumérateur pour itérer au sein de les structures de **FORMATETC** prises en charge par l'objet de données.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IDataObjectImpl::FireDataChange](../Topic/IDataObjectImpl::FireDataChange.md)|Envoie une notification de modifications dans chaque récepteurs de notifications.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](../Topic/IDataObjectImpl::GetCanonicalFormatEtc.md)|Extrait une structure logique de **FORMATETC** équivalente à une qui est plus complexe.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IDataObjectImpl::GetData](../Topic/IDataObjectImpl::GetData.md)|Transfère les données de l'objet de données au client.  Les données sont décrites dans une structure de **FORMATETC** et sont transférées via une structure de **STGMEDIUM** .|  
|[IDataObjectImpl::GetDataHere](../Topic/IDataObjectImpl::GetDataHere.md)|Semblable à `GetData`, à moins que le client ne allouer la structure de **STGMEDIUM** .  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IDataObjectImpl::QueryGetData](../Topic/IDataObjectImpl::QueryGetData.md)|Détermine si l'objet de données prend en charge une structure spécifique de **FORMATETC** pour transférer des données.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IDataObjectImpl::SetData](../Topic/IDataObjectImpl::SetData.md)|Transfère les données du client à l'objet de données.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
  
## Notes  
 L'interface d' [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) fournit des méthodes à l'Uniform Data Transfer de charge.  `IDataObject` utilise les structures [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) et [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) de format standard pour récupérer et stocker des données.  
  
 `IDataObject` gère également les connexions aux récepteurs de notifications des notifications de modification des données du handle.  Pour que le client reçoit des notifications de modification de données de l'objet de données, le client doit implémenter l'interface d' [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) sur un objet appelé un récepteur de notifications.  Lorsque le client appelle ensuite **IDataObject::DAdvise**, une connexion établie entre l'objet de données et le récepteur de notifications.  
  
 La classe `IDataObjectImpl` fournit une implémentation par défaut d' `IDataObject` et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)