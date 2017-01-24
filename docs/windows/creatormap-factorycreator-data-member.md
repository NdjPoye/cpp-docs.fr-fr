---
title: "CreatorMap::factoryCreator, donn&#233;es de membre | Microsoft Docs"
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
  - "module/Microsoft::WRL::Details::CreatorMap::factoryCreator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "factoryCreator (membre de données)"
ms.assetid: c9aac363-8f38-4cfd-9605-1e6ac74c5097
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CreatorMap::factoryCreator, donn&#233;es de membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
HRESULT (*factoryCreator)(  
   unsigned int* currentflags,  
   const CreatorMap* entry,  
   REFIID iidClassFactory,  
 IUnknown** factory);  
```  
  
## Paramètres  
 `currentflags`  
 L'un des énumérateurs de type [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
 `entry`  
 Un CreatorMap.  
  
 `iidClassFactory`  
 L'ID d'interface d'une fabrique de classe.  
  
 `factory`  
 Lorsque l'opération se termine, l'adresse d'une fabrique de classe.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi ; sinon, un HRESULT indiquant l'erreur.  
  
## Notes  
 Crée une fabrique pour le CreatorMap spécifié.  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [CreatorMap, structure](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)