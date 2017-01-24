---
title: "_com_ptr_t::Release | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t.Release"
  - "_com_ptr_t::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "release (méthode)"
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::Release
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Appelle la fonction membre **Release** de **IUnknown** sur le pointeur d'interface encapsulé.  
  
## Syntaxe  
  
```  
  
void Release( );  
  
```  
  
## Notes  
 Appelle `IUnknown::Release` sur le pointeur d'interface encapsulé, ce qui déclenche une erreur `E_POINTER` si ce pointeur d'interface est **NULL**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_ptr\_t, classe](../cpp/com-ptr-t-class.md)