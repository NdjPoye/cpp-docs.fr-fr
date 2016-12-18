---
title: "ModuleBase, classe | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::ModuleBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ModuleBase (classe)"
ms.assetid: edce7591-6893-46f7-94a7-382827775548
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ModuleBase, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l’infrastructure/FAO et n’est pas destinée à être utilisée directement à partir de votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class ModuleBase;  
```  
  
## <a name="remarks"></a>Notes  
 Représente la classe de base de la [Module](../windows/module-class.md) classes.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Modulebase::modulebase, constructeur](../windows/modulebase-modulebase-constructor.md)|Initialise une instance de la classe de Module.|  
|[ModuleBase :: ~ ModuleBase, destructeur](../windows/modulebase-tilde-modulebase-destructor.md)|Deinitializes l’instance actuelle de la classe de Module.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Modulebase::decrementobjectcount, méthode](../windows/modulebase-decrementobjectcount-method.md)|En cas d’implémentation, décrémente le nombre d’objets suivis par le module.|  
|[Modulebase::incrementobjectcount, méthode](../windows/modulebase-incrementobjectcount-method.md)|En cas d’implémentation, incrémente le nombre d’objets suivis par le module.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ModuleBase`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::wrl::Details Namespace](../windows/microsoft-wrl-details-namespace.md)