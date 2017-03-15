---
title: "RemoveReference, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::RemoveReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RemoveReference (structure)"
ms.assetid: 43ff91bb-815a-440e-b9fb-7dcbb7c863af
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RemoveReference, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template<  
   class T  
>  
struct RemoveReference;  
template<  
   class T  
>  
struct RemoveReference<T&>;  
template<  
   class T  
>  
struct RemoveReference<T&&>;  
```  
  
#### Paramètres  
 `T`  
 Une classe.  
  
## Notes  
 Élimine la fonctionnalité de référence ou de référence rvalue du paramètre de modèle de classe spécifié.  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`Type`|Synonyme du paramètre du modèle de classe.|  
  
## Hiérarchie d'héritage  
 `RemoveReference`  
  
## Configuration requise  
 **En\-tête:** internal.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)