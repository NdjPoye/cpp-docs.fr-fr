---
title: "VerifyInheritanceHelper::Verify, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verify (méthode)"
ms.assetid: 3360082b-81ad-4191-9ec3-b4372f7207d7
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# VerifyInheritanceHelper::Verify, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
static void Verify();  
```  
  
## Remarques  
 Teste les deux interfaces spécifiées par les paramètres de modèle actuels et détermine si une interface est dérivée de l'autre.  
  
 Une erreur est émise si une interface n'est pas dérivée de l'autre.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [VerifyInheritanceHelper, structure](../windows/verifyinheritancehelper-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)