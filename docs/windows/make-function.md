---
title: "Make, fonction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Make"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Make (fonction)"
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Make, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise la classe [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] spécifiée.  Utilisez cette fonction pour instancier un composant qui est défini dans le même module.  
  
## Syntaxe  
  
```  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8,  
   TArg9 &&arg9  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2  
);  
template <  
   typename T,  
   typename TArg1  
>  
ComPtr<T> Make(  
   TArg1 &&arg1  
);  
template <  
   typename T  
>  
ComPtr<T> Make();  
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
 Un Objet `ComPtr<T>` en cas de réussite ; sinon, `nullptr`.  
  
## Remarques  
 Consultez [Comment : instancier directement les composants WRL](../windows/how-to-instantiate-wrl-components-directly.md) pour connaître les différences entre ces fonctions et [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md), et pour un exemple.  
  
## Configuration requise  
 **En\-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)