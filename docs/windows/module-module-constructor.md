---
title: "Module::Module, constructeur | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::Module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Module, constructeur"
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::Module, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe de Module.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Module();  
```  
  
## <a name="remarks"></a>Notes  
 Ce constructeur est protégé et ne peut pas être appelé avec le `new` (mot clé). Au lieu de cela, appelez [module::GetModule, méthode](../windows/module-getmodule-method.md) ou [module::Create, méthode](../windows/module-create-method.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)