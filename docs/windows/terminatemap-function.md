---
title: "TerminateMap, fonction | Microsoft Docs"
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
  - "module/Microsoft::WRL::Details::TerminateMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TerminateMap (fonction)"
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TerminateMap, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l’infrastructure/FAO et n’est pas destinée à être utilisée directement à partir de votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
## <a name="parameters"></a>Paramètres  
 `module`  
 Un [module](../windows/module-class.md).  
  
 `serverName`  
 Le nom d’un sous-ensemble des fabriques de classes dans le module spécifié par le paramètre `module`.  
  
 `forceTerminate`  
 `true` Pour mettre fin à la classe fabriques, quelle que soit leur sont actifs ; `false` arrêt ne pas les fabriques de classe si n’importe quel fabrique est actif.  
  
## <a name="return-value"></a>Valeur de retour  
 `true` Si toutes les fabriques de classe ont été arrêtées ; dans le cas contraire, `false`.  
  
## <a name="remarks"></a>Notes  
 Arrête les fabriques de classe dans le module spécifié.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::wrl::Details Namespace](../windows/microsoft-wrl-details-namespace.md)