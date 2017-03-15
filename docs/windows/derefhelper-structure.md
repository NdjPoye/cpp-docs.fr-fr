---
title: "DerefHelper, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::Details::DerefHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DerefHelper (structure)"
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# DerefHelper, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename T  
>  
struct DerefHelper;  
  
template <  
   typename T  
>  
struct DerefHelper<T*>;  
```  
  
#### Paramètres  
 `T`  
 Un paramètre de modèle.  
  
## Remarques  
 Représente un pointeur déréférencé vers le paramètre de modèle `T*`.  
  
 DerefHelper est utilisé dans une expression telle que: `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`.  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`DerefType`|Identificateur du paramètre de modèle déréférencé `T*`.|  
  
## Hiérarchie d'héritage  
 `DerefHelper`  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)