---
title: "ImplementsHelper::CastToUnknown, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown (méthode)"
ms.assetid: 5bcfcbaf-c75f-4d43-87b3-0d6838c838d9
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ImplementsHelper::CastToUnknown, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
IUnknown* CastToUnknown();  
```  
  
## Valeur de retour  
 Pointeur vers l'interface IUnknown sous\-jacente.  
  
## Notes  
 Obtient un pointeur vers l'interface IUnknown sous\-jacente pour la structure Implements actuelle.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [ImplementsHelper, structure](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)