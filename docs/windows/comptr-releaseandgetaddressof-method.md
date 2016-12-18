---
title: "ComPtr::ReleaseAndGetAddressOf, m&#233;thode | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAndGetAddressOf (méthode)"
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::ReleaseAndGetAddressOf, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libère l'interface associée à ce ComPtr puis récupère l'adresse du membre de données [ptr\_](../windows/comptr-ptr-data-member.md), qui contient un pointeur vers l'interface fournie.  
  
## Syntaxe  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## Valeur de retour  
 L'adresse de la donnée membre [ptr\_](../windows/comptr-ptr-data-member.md) de ce ComPtr.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)   
 [ComPtr::ptr\_, données de membre](../windows/comptr-ptr-data-member.md)