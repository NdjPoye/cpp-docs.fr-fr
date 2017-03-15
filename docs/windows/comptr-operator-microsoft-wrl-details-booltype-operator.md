---
title: "ComPtr::operator Microsoft::WRL::Details::BoolType, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator Microsoft::WRL::Details::BoolType, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si un ComPtr gère la durée de vie d'une interface ou non.  
  
## Syntaxe  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## Valeur de retour  
 Si une interface est associée à ce ComPtr, l'adresse du membre de données [BoolStruct::Member](../windows/boolstruct-member-data-member.md); sinon, `nullptr`.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)   
 [ComPtr::Get, méthode](../windows/comptr-get-method.md)