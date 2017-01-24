---
title: "MakeAndInitialize, fonction | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::MakeAndInitialize"
dev_langs: 
  - "C++"
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MakeAndInitialize, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise la classe [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] spécifiée.  Utilisez cette fonction pour instancier un composant qui est défini dans le même module.  
  
## Syntaxe  
  
```cpp  
template <typename T, typename I,   
typename TArg1,   
typename TArg2,   
typename TArg3,   
typename TArg4,   
typename TArg5,   
typename TArg6,   
typename TArg7,   
typename TArg8,   
typename TArg9> HRESULT MakeAndInitialize(_Outptr_result_nullonfailure_ I** ppvObject, TArg1 &&arg1, TArg2 &&arg2, TArg3 &&arg3, TArg4 &&arg4, TArg5 &&arg5, TArg6 &&arg6, TArg7 &&arg7, TArg8 &&arg8, TArg9 &&arg9) throw()  
  
```  
  
#### Paramètres  
 `T`  
 Une classe spécifiée par l'utilisateur qui hérite de `WRL::RuntimeClass`.  
  
 `TArg1`  
 Type de l'argument 1 passé à la classe d'exécution spécifiée.  
  
 `TArg2`  
 Type de l'argument 2 passé à la classe d'exécution spécifiée.  
  
 `TArg3`  
 Type de l'argument 3 passé à la classe d'exécution spécifiée.  
  
 `TArg4`  
 Type de l'argument 4 passé à la classe d'exécution spécifiée.  
  
 `TArg5`  
 Type de l'argument 5 passé à la classe d'exécution spécifiée.  
  
 `TArg6`  
 Type de l'argument 6 passé à la classe d'exécution spécifiée.  
  
 `TArg7`  
 Type de l'argument 7 passé à la classe d'exécution spécifiée.  
  
 `TArg8`  
 Type de l'argument 8 passé à la classe d'exécution spécifiée.  
  
 `TArg9`  
 Type de l'argument 9 passé à la classe d'exécution spécifiée.  
  
 `arg1`  
 L'argument 1 passé à la classe d'exécution spécifiée.  
  
 `arg2`  
 L'argument 2 passé à la classe d'exécution spécifiée.  
  
 `arg3`  
 L'argument 3 passé à la classe d'exécution spécifiée.  
  
 `arg4`  
 L'argument 4 passé à la classe d'exécution spécifiée.  
  
 `arg5`  
 L'argument 5 passé à la classe d'exécution spécifiée.  
  
 `arg6`  
 L'argument 6 passé à la classe d'exécution spécifiée.  
  
 `arg7`  
 L'argument 7 passé à la classe d'exécution spécifiée.  
  
 `arg8`  
 L'argument 8 passé à la classe d'exécution spécifiée.  
  
 `arg9`  
 L'argument 9 passé à la classe d'exécution spécifiée.  
  
## Valeur de retour  
 Valeur `HRESULT`.  
  
## Remarques  
 Consultez [Comment : instancier directement les composants WRL](../windows/how-to-instantiate-wrl-components-directly.md) pour connaître les différences entre cette fonction et [Microsoft::WRL::Details::MakeAndInitialize](../windows/make-function.md), et pour un exemple.  
  
## Configuration requise  
 **En\-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)