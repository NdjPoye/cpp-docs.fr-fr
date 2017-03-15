---
title: "Module::UnregisterObjects, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::UnregisterObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterObjects (méthode)"
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Module::UnregisterObjects, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Annule l’inscription d’objets dans le module spécifié afin que les autres applications ne peuvent pas se connecter à leur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT UnregisterObjects(  
   ModuleBase* module,  
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `module`  
 Pointeur vers un module.  
  
 `serverName`  
 Nom de qualification qui spécifie un sous-ensemble des objets affectés par cette opération.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si cette opération est réussie ; Sinon, une erreur HRESULT qui indique la raison pour laquelle cette opération a échoué.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)