---
title: "ImplementsHelper, structure | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::ImplementsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ImplementsHelper (structure)"
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ImplementsHelper, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### Paramètres  
 `RuntimeClassFlagsT`  
 Un champ des flags spécifiant un ou plusieurs énumérateurs de type [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
 `ILst`  
 Une liste d'IDs d'interface.  
  
 `IsDelegateToClass`  
 Spécifie `true` si l'instance actuelle d'Implements est une classe de base du premier ID d'interface dans `ILst`; sinon, `false`.  
  
## Remarques  
 Aide à l'implémentation de la structure [Impléments](../windows/implements-structure.md).  
  
 Ce modèle parcourt une liste d'interfaces et les ajoute en tant que des classes de base et informations nécessaires à l'activation de QueryInterface.  
  
## Membres  
  
## Hiérarchie d'héritage  
 `ImplementsHelper`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/fr-fr/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)