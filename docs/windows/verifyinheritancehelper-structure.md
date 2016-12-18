---
title: "VerifyInheritanceHelper, structure | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::VerifyInheritanceHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VerifyInheritanceHelper (structure)"
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# VerifyInheritanceHelper, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename I,  
   typename Base  
>  
struct VerifyInheritanceHelper;  
template <  
   typename I  
>  
struct VerifyInheritanceHelper<I, Nil>;  
```  
  
#### Paramètres  
 `I`  
 Un type.  
  
 `Base`  
 Un autre type.  
  
## Notes  
 Teste si une interface est dérivée d'une autre interface.  
  
## Membres  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[VerifyInheritanceHelper::Verify, méthode](../windows/verifyinheritancehelper-verify-method.md)|Teste les deux interfaces spécifiées par les paramètres de modèle actuels et détermine si une interface est dérivée de l'autre.|  
  
## Hiérarchie d'héritage  
 `VerifyInheritanceHelper`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)