---
title: "CComClassFactory Class | Microsoft Docs"
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
  - "ATL.CComClassFactory"
  - "CComClassFactory"
  - "ATL::CComClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactory class"
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComClassFactory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente l'interface d' [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) .  
  
## Syntaxe  
  
```  
  
   class CComClassFactory : public IClassFactory,   
public CComObjectRootEx< CComGlobalsThreadModel >  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComClassFactory::CreateInstance](../Topic/CComClassFactory::CreateInstance.md)|Crée un objet de le CLSID spécifié.|  
|[CComClassFactory::LockServer](../Topic/CComClassFactory::LockServer.md)|Verrouille la fabrique de classe en mémoire.|  
  
## Notes  
 `CComClassFactory` implémente l'interface d' [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) , qui contient des méthodes pour créer un objet CLSID particulier, ainsi que verrouille la fabrique de classe en mémoire pour permettre de nouveaux objets à créer plus rapidement.  **IClassFactory** doit être implémenté pour chaque classe à que vous stockez dans la base de registres et que vous assignez à le CLSID.  
  
 Les objets ATL dans normalement une fabrique de classe en dérivant de [CComCoClass](../../atl/reference/ccomcoclass-class.md).  Cette classe inclut un [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md), qui déclare `CComClassFactory` comme une fabrique de classe par défaut.  Pour remplacer cette valeur par défaut, spécifiez l'une des macros d' `DECLARE_CLASSFACTORY`*XXX* dans la définition de classe.  Par exemple, la macro de [DECLARE\_CLASSFACTORY\_EX](../Topic/DECLARE_CLASSFACTORY_EX.md) utilise la classe spécifiée pour la fabrique de classe :  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/CPP/ccomclassfactory-class_1.h)]  
  
 La définition de classe ci\-dessus spécifie que **CMyClassFactory** sera utilisé comme fabrique de classe par défaut de l'objet.  **CMyClassFactory** doit dériver d' `CComClassFactory` et remplacer `CreateInstance`.  
  
 ATL fournit trois autres macros qui déclarent une fabrique de classe :  
  
-   [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) utilise [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), qui contrôle la création par une licence.  
  
-   [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) utilise [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), qui crée des objets dans plusieurs des apartments.  
  
-   [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md) utilise [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), qui crée un objet unique de [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) .  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)