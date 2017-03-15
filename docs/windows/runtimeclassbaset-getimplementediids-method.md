---
title: "RuntimeClassBaseT::GetImplementedIIDS, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetImplementedIIDS (méthode)"
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClassBaseT::GetImplementedIIDS, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT GetImplementedIIDS(  
   _In_ T* implements,  
   _Out_ ULONG *iidCount,  
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids  
);  
```  
  
#### Paramètres  
 `T`  
 Type du paramètre `implements`.  
  
 `implements`  
 Pointeur vers le type spécifié par le paramètre `T`.  
  
 `iidCount`  
 Le nombre maximum d'IDs d'interface à récupérer.  
  
 `iids`  
 Si cette opération est terminée avec succès, un tableau des IDs d'interface implémenté par type `T`.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT décrivant l'erreur.  
  
## Notes  
 Récupère un tableau d'IDs d'interface implémentés par un type spécifié.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [RuntimeClassBaseT, structure](../windows/runtimeclassbaset-structure.md)