---
title: "IObjectSafetyImpl Class | Microsoft Docs"
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
  - "IObjectSafetyImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [ATL], safe"
  - "IObjectSafety, ATL (implémentation)"
  - "IObjectSafetyImpl class"
  - "safe for scripting and initialization (controls)"
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IObjectSafetyImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit une implémentation par défaut de l'interface d' `IObjectSafety` pour permettre à un client pour récupérer et définir les niveaux de sécurité d'un objet.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template <class   
      T  
      , DWORD   
      dwSupportedSafety  
      >  
class IObjectSafetyImpl  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 Spécifie les options prises de sécurité pour le contrôle.  Peut avoir l'une des valeurs suivantes :  
  
-   **INTERFACESAFE\_FOR\_UNTRUSTED\_CALLER** l'interface identifié par le paramètre `riid` de [SetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::SetInterfaceSafetyOptions.md) doit être rendu sécurisé pour le script.  
  
-   **INTERFACESAFE\_FOR\_UNTRUSTED\_DATA** l'interface identifié par le paramètre `riid` d' `SetInterfaceSafetyOptions` doit être rendu sécurisé pour les données non fiables pendant l'initialisation.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::GetInterfaceSafetyOptions.md)|Récupère les options de sécurité prises en charge par l'objet, ainsi que les options de sécurité actuellement définies pour l'objet.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::SetInterfaceSafetyOptions.md)|Effectue le coffre\-fort d'objet pour l'initialisation ou le script.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IObjectSafetyImpl::m\_dwCurrentSafety](../Topic/IObjectSafetyImpl::m_dwCurrentSafety.md)|Stocke le niveau en cours de sécurité de l'objet.|  
  
## Notes  
 La classe `IObjectSafetyImpl` fournit une implémentation par défaut d' `IObjectSafety`.  L'interface d' `IObjectSafety` permet à un client pour récupérer et définir les niveaux de sécurité d'un objet.  Par exemple, un navigateur web peut appeler **IObjectSafety::SetInterfaceSafetyOptions** pour qu'un coffre\-fort de contrôle de l'initialisation ou sécurisé pour le script.  
  
 Notez qu'à l'aide de la macro d' [IMPLEMENTED\_CATEGORY](../Topic/IMPLEMENTED_CATEGORY.md) avec **CATID\_SafeForScripting** et les catégories de composants de **CATID\_SafeForInitializing** fournit une autre manière de spécifier qu'un composant est sécurisé.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [IObjectSafety Interface](https://msdn.microsoft.com/en-us/library/aa768224.aspx)   
 [Class Overview](../../atl/atl-class-overview.md)