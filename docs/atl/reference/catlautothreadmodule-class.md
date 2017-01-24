---
title: "CAtlAutoThreadModule Class | Microsoft Docs"
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
  - "ATL.CAtlAutoThreadModule"
  - "CAtlAutoThreadModule"
  - "ATL::CAtlAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlAutoThreadModule class"
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlAutoThreadModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente un regroupé par thread, serveur COM de modèle cloisonné.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      class CAtlAutoThreadModule :  
public CAtlAutoThreadModuleT< CAtlAutoThreadModule >  
```  
  
## Notes  
 `CAtlAutoThreadModule` dérive de [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) et implémente un regroupé par thread, serveur COM de modèle cloisonné.  `CAtlAutoThreadModule` utilise [CComApartment](../../atl/reference/ccomapartment-class.md) pour gérer un " apartment " pour chaque thread dans le module.  
  
 Vous devez utiliser la macro de [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) dans la définition de classe de votre objet pour spécifier [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) comme une fabrique de classe.  Vous devez ensuite ajouter une seule instance d'une classe dérivée d' `CAtlAutoThreadModuleT` tel qu' `CAtlAutoThreadModule`.  Par exemple :  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  Cette classe substitue la classe obsolète de [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) .  
  
## Hiérarchie d'héritage  
 `IAtlAutoThreadModule`  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 `CAtlAutoThreadModule`  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [CAtlAutoThreadModuleT Class](../../atl/reference/catlautothreadmodulet-class.md)   
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Module, classes](../../atl/atl-module-classes.md)