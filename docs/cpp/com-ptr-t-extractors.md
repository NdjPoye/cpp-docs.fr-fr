---
title: "_com_ptr_t, extracteurs | Microsoft Docs"
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
  - "_com_ptr_t::operatorInterface&"
  - "operatorInterface*"
  - "operatorInterface&"
  - "_com_ptr_t::operatorbool"
  - "_com_ptr_t.operator->"
  - "_com_ptr_t.operator*"
  - "_com_ptr_t::operator->"
  - "_com_ptr_t::operator*"
  - "_com_ptr_t.operatorInterface&"
  - "_com_ptr_t.operatorbool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& (opérateur), avec des objets spécifiques"
  - "* (opérateur), avec des objets spécifiques"
  - "-> (opérateur), avec des objets spécifiques"
  - "extracteurs"
  - "extracteurs, _com_ptr_t (classe)"
  - "* (opérateur)"
  - "bool (opérateur)"
  - "Interface& (opérateur)"
  - "Interface* (opérateur)"
  - "& (opérateur)"
  - "* (opérateur)"
  - "-> (opérateur)"
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t, extracteurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Récupérez le pointeur d'interface COM encapsulé.  
  
## Syntaxe  
  
```  
  
      operator Interface*( ) const throw( );   
operator Interface&( ) const;   
Interface& operator*( ) const;   
Interface* operator->( ) const;   
Interface** operator&( ) throw( );   
operator bool( ) const throw( );  
```  
  
## Notes  
  
-   **operator Interface\*** Retourne le pointeur d'interface encapsulé, qui peut être **NULL**.  
  
-   **operator Interface&** Retourne une référence au pointeur d'interface encapsulé et émet une erreur si le pointeur est **NULL**.  
  
-   **operator\*** Permet à un objet pointeur intelligent d'agir comme s'il s'agissait de l'interface encapsulée réelle, une fois déréférencé.  
  
-   **operator\-\>** Permet à un objet pointeur intelligent d'agir comme s'il s'agissait de l'interface encapsulée réelle, une fois déréférencé.  
  
-   **operator&** Libère tout pointeur d'interface encapsulé en le remplaçant par **NULL** et retourne l'adresse du pointeur encapsulé.  Cela permet de passer par adresse le pointeur intelligent à une fonction qui possède un paramètre **out** via lequel elle retourne un pointeur d'interface.  
  
-   **operator bool** Permet d'utiliser un objet pointeur intelligent dans une expression conditionnelle.  Cet opérateur retourne **true** si le pointeur n'est pas **NULL**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_ptr\_t, classe](../cpp/com-ptr-t-class.md)