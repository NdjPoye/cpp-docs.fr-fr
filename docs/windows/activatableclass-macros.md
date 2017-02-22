---
title: "ActivatableClass, macros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ActivatableClass"
  - "ActivatableClassWithFactory"
  - "ActivatableClassWithFactoryEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivatableClassWithFactory"
  - "ActivatableClass"
  - "ActivatableClassWithFactoryEx"
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ActivatableClass, macros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Remplit un cache interne qui contient une fabrique qui peut créer une instance de la classe spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
ActivatableClass(  
   className  
);  
  
ActivatableClassWithFactory(  
   className,   
   factory  
);  
  
ActivatableClassWithFactoryEx(  
   className,   
   factory,   
   serverName  
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `className`  
 Nom de la classe à créer.  
  
 `factory`  
 Fabrique qui crée une instance de la classe spécifiée.  
  
 `serverName`  
 Nom qui spécifie un sous-ensemble des fabriques du module.  
  
## <a name="remarks"></a>Notes  
 Ne pas utiliser ces macros avec COM classique, sauf si vous utilisez la `#undef` directive pour vous assurer que les **__WRL_WINRT_STRICT\_\_** définition de macro est supprimée.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)