---
title: "_com_ptr_t::Detach | Microsoft Docs"
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
  - "_com_ptr_t::Detach"
  - "_com_ptr_t.Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach (méthode)"
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Extrait et retourne le pointeur d'interface encapsulé.  
  
## Syntaxe  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## Notes  
 Extrait et retourne le pointeur d'interface encapsulé, puis efface le stockage du pointeur encapsulé en lui affectant la valeur **NULL**.  Cela supprime le pointeur d'interface de l'encapsulation.  Il vous appartient d'appeler **Release** sur le pointeur d'interface retourné.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_ptr\_t, classe](../cpp/com-ptr-t-class.md)