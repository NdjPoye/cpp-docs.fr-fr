---
title: "_com_ptr_t::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::Attach"
  - "_com_ptr_t.Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach (méthode)"
  - "interfaces COM, attacher pointeur"
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Encapsule un pointeur d'interface brut du type de ce pointeur intelligent.  
  
## Syntaxe  
  
```  
  
      void Attach(  
   Interface* pInterface   
) throw( );  
void Attach(  
   Interface* pInterface,  
   bool fAddRef   
) throw( );  
```  
  
#### Paramètres  
 `pInterface`  
 Pointeur d'interface brut.  
  
 `fAddRef`  
 Si la valeur est **true**, alors `AddRef` est appelé.  Si elle est **false**, l'objet `_com_ptr_t` prend la propriété du pointeur d'interface brut sans appeler `AddRef`.  
  
## Notes  
  
-   **Attacher\(**  `pInterface`  **\)** `AddRef` n'est pas appelé.  La propriété de l'interface est passée à cet objet `_com_ptr_t`.  **Release** est appelé pour décrémenter le décompte de références du pointeur précédemment encapsulé.  
  
-   **Attacher\(**  `pInterface` **,**  `fAddRef`  **\)** Si la valeur`fAddRef` est **true**, `AddRef` est appelé pour incrémenter le décompte de références du pointeur d'interface encapsulé.  Si `fAddRef` est **false**, cet objet `_com_ptr_t` prend la propriété du pointeur d'interface brut sans appeler `AddRef`.  **Release** est appelé pour décrémenter le décompte de références du pointeur précédemment encapsulé.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_ptr\_t, classe](../cpp/com-ptr-t-class.md)