---
title: "CComClassFactoryAutoThread Class | Microsoft Docs"
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
  - "ATL::CComClassFactoryAutoThread"
  - "ATL.CComClassFactoryAutoThread"
  - "CComClassFactoryAutoThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactoryAutoThread class"
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComClassFactoryAutoThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente l'interface d' [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) , et autorise les objets à créer dans plusieurs des apartments.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      class CComClassFactoryAutoThread : public IClassFactory,   
public CComObjectRootEx< CComGlobalsThreadModel >  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComClassFactoryAutoThread::CreateInstance](../Topic/CComClassFactoryAutoThread::CreateInstance.md)|Crée un objet de le CLSID spécifié.|  
|[CComClassFactoryAutoThread::LockServer](../Topic/CComClassFactoryAutoThread::LockServer.md)|Verrouille la fabrique de classe en mémoire.|  
  
## Notes  
 `CComClassFactoryAutoThread` est semblable à [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), mais autorise les objets à créer dans plusieurs des apartments.  Pour tirer parti de cette prise en charge, dérivez votre package EXE de [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Les objets ATL dans normalement une fabrique de classe en dérivant de [CComCoClass](../../atl/reference/ccomcoclass-class.md).  Cette classe inclut un [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md), qui déclare [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) comme une fabrique de classe par défaut.  Pour utiliser `CComClassFactoryAutoThread`, spécifiez la macro de [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) dans la définition de classe de votre objet.  Par exemple :  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/CPP/ccomclassfactoryautothread-class_1.h)]  
  
## Hiérarchie d'héritage  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 Class](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactorySingleton Class](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)