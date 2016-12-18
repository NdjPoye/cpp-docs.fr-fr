---
title: "RuntimeClassBaseT, structure | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT"
dev_langs: 
  - "C++"
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClassBaseT, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   unsigned int RuntimeClassTypeT  
>  
friend struct Details::RuntimeClassBaseT;  
```  
  
#### Paramètres  
 `RuntimeClassTypeT`  
 Un champ des flags spécifiant un ou plusieurs énumérateurs de type [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
## Notes  
 Fournit des méthodes d'assistance pour les opérations `QueryInterface` et l'obtention d'IDs d'interface.  
  
## Membres  
  
## Hiérarchie d'héritage  
 `RuntimeClassBaseT`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/fr-fr/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)