---
title: "IsSame, structure | Microsoft Docs"
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
  - "internal/Microsoft::WRL::Details::IsSame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsSame (structure)"
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IsSame, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename T1,  
   typename T2  
>  
struct IsSame;  
template <  
   typename T1  
>  
struct IsSame<T1, T1>;  
```  
  
#### Paramètres  
 `T1`  
 Un type.  
  
 `T2`  
 Un autre type.  
  
## Notes  
 Teste si un type spécifié est le même qu'un autre type spécifié.  
  
## Membres  
  
### Constantes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[IsSame::value, constante](../windows/issame-value-constant.md)|Indique si un type est identique à un autre.|  
  
## Hiérarchie d'héritage  
 `IsSame`  
  
## Configuration requise  
 **En\-tête:** internal.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)