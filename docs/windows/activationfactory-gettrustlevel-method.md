---
title: "ActivationFactory::GetTrustLevel, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::GetTrustLevel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetTrustLevel (méthode)"
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::GetTrustLevel, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient le niveau de confiance de l'objet qu'instancie l'ActivationFactory actuelle.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### Paramètres  
 `trustLvl`  
 Lorsque cette opération se termine, le niveau de confiance de la classe d'exécution que l'ActivationFactory instancie.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, une erreur d'assertion est émise et le `trustLvl` est défini à FullTrust.  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ActivationFactory, classe](../windows/activationfactory-class.md)