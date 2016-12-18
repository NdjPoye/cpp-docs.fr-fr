---
title: "InterfaceTraits::FillArrayWithIid, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid (méthode)"
ms.assetid: 73583177-adc9-4fcb-917d-fa7e6d07c990
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InterfaceTraits::FillArrayWithIid, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
  
```  
  
#### Paramètres  
 `index`  
 Pointeur vers un champ qui contient une valeur d'index de base zéro.  
  
 `iids`  
 Un tableau d'IDs d'interface.  
  
## Remarques  
 Assigne l'ID d'interface de `Base` à l'élément de tableau spécifié par l'argument d'index.  
  
 Contrairement au nom de cette API, un seul élément du tableau est modifié; pas le tableau entièr.  
  
 Pour plus d'informations sur `Base`, consultez la section Typedefs Publiques dans [InterfaceTraits, structure](../windows/interfacetraits-structure.md).  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [InterfaceTraits, structure](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)