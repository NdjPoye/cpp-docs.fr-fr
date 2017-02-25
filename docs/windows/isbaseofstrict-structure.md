---
title: "IsBaseOfStrict, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::IsBaseOfStrict"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsBaseOfStrict (structure)"
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IsBaseOfStrict, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
#### Paramètres  
 `Base`  
 Type de base.  
  
 `Derived`  
 Le type dérivé.  
  
## Remarques  
 Teste si un type est la base d'un autre.  
  
 Le premier modèle teste si un type est dérivé d'un type de base, qui peut donner **true** ou **false**.  Le second modèle teste si un type est dérivé de lui\-même, ce qui donne toujours **false**.  
  
## Membres  
  
### Constantes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[IsBaseOfStrict::value, constante](../windows/isbaseofstrict-value-constant.md)|Inidique si un type est la base d'un autre.|  
  
## Hiérarchie d'héritage  
 `IsBaseOfStrict`  
  
## Configuration requise  
 **En\-tête:** internal.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)