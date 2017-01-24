---
title: "CAtlDllModuleT Class | Microsoft Docs"
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
  - "ATL.CAtlDllModuleT"
  - "ATL::CAtlDllModuleT<T>"
  - "ATL::CAtlDllModuleT"
  - "ATL.CAtlDllModuleT<T>"
  - "CAtlDllModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlDllModuleT class"
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlDllModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente le package pour une DLL.  
  
## Syntaxe  
  
```  
  
      template <  
   class T   
>  
class ATL_NO_VTABLE CAtlDllModuleT :  
   public CAtlModuleT< T >  
```  
  
#### Paramètres  
 `T`  
 Votre classe dérivée d' `CAtlDllModuleT`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlDllModuleT::CAtlDllModuleT](../Topic/CAtlDllModuleT::CAtlDllModuleT.md)|Constructeur.|  
|[CAtlDllModuleT::~CAtlDllModuleT](../Topic/CAtlDllModuleT::~CAtlDllModuleT.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlDllModuleT::DllCanUnloadNow](../Topic/CAtlDllModuleT::DllCanUnloadNow.md)|Teste si la DLL peut être déchargé.|  
|[CAtlDllModuleT::DllGetClassObject](../Topic/CAtlDllModuleT::DllGetClassObject.md)|Retourne une fabrique de classe.|  
|[CAtlDllModuleT::DllMain](../Topic/CAtlDllModuleT::DllMain.md)|Le point d'entrée facultatif dans une bibliothèque de liens dynamiques \(DLL\).|  
|[CAtlDllModuleT::DllRegisterServer](../Topic/CAtlDllModuleT::DllRegisterServer.md)|Ajoute des entrées dans la base de registres pour les objets dans la DLL.|  
|[CAtlDllModuleT::DllUnregisterServer](../Topic/CAtlDllModuleT::DllUnregisterServer.md)|Supprime les entrées dans la base de registres pour les objets dans la DLL.|  
|[CAtlDllModuleT::GetClassObject](../Topic/CAtlDllModuleT::GetClassObject.md)|Retourne une fabrique de classe.  Appelé par [DllGetClassObject](../Topic/CAtlDllModuleT::DllGetClassObject.md).|  
  
## Notes  
 `CAtlDllModuleT` représente le package pour une bibliothèque de liens dynamiques \(DLL\) et fournit des fonctions utilisées par tous les projets de DLL.  Cette spécialisation de classe de [CAtlModuleT](../../atl/reference/catlmodulet-class.md) inclut la prise en charge de l'inscription.  
  
 Pour plus d'informations sur les modules dans ATL, consultez [Classes de module ATL](../../atl/atl-module-classes.md).  
  
## Hiérarchie d'héritage  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlDllModuleT`  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [CAtlModuleT Class](../../atl/reference/catlmodulet-class.md)   
 [CAtlExeModuleT Class](../../atl/reference/catlexemodulet-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Module, classes](../../atl/atl-module-classes.md)