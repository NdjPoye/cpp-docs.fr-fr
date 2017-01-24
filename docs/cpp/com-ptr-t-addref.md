---
title: "_com_ptr_t::AddRef | Microsoft Docs"
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
  - "_com_ptr_t::AddRef"
  - "_com_ptr_t.AddRef"
  - "AddRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef (méthode) (C++), pointeur d'interface"
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::AddRef
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Appelle la fonction membre `AddRef` de **IUnknown** sur le pointeur d'interface encapsulé.  
  
## Syntaxe  
  
```  
  
void AddRef( );  
  
```  
  
## Notes  
 Appelle `IUnknown::AddRef` sur le pointeur d'interface encapsulé, ce qui génère une erreur `E_POINTER` si le pointeur est **NULL**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_ptr\_t, classe](../cpp/com-ptr-t-class.md)