---
title: "EnableIf, structure | Microsoft Docs"
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
  - "internal/Microsoft::WRL::Details::EnableIf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EnableIf (structure)"
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EnableIf, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   bool b,  
   typename T = void  
>  
  
struct EnableIf;  
template <  
   typename T  
>  
struct EnableIf<true, T>;  
```  
  
#### Paramètres  
 `T`  
 Un type.  
  
 `b`  
 Expression booléenne.  
  
## Notes  
 Définit une donnée membre du type spécifié par le deuxième paramètre de modèle si le premier correspond à `true`.  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`type`|Si le paramètre de modèle `b` correspond à `true`, la spécialisation partielle définit la donnée membre `type` comme étant de type `T`.|  
  
## Hiérarchie d'héritage  
 `EnableIf`  
  
## Configuration requise  
 **En\-tête:** internal.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)