---
title: _com_ptr_t, extracteurs | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
dev_langs: C++
helpviewer_keywords:
- operator Interface& [C++]
- '* operator [C++], with specific objects'
- operator& [C++]
- operator* [C++]
- -> operator [C++], with specific objects
- '& operator [C++], with specific objects'
- operator Interface* [C++]
- operator * [C++]
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors [C++]
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73e2dca693939765e700d51b6caab0815c6d5e7e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrt-extractors"></a>_com_ptr_t, extracteurs
**Section spécifique à Microsoft**  
  
 Récupérez le pointeur d'interface COM encapsulé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      operator Interface*( ) const throw( );   
operator Interface&( ) const;   
Interface& operator*( ) const;   
Interface* operator->( ) const;   
Interface** operator&( ) throw( );   
operator bool( ) const throw( );  
```  
  
## <a name="remarks"></a>Remarques  
  
-   **Interface d’opérateur\***  retourne le pointeur d’interface encapsulé, qui peut être **NULL**.  
  
-   **operator Interface &** retourne une référence au pointeur d’interface encapsulé et émet une erreur si le pointeur est **NULL**.  
  
-   **opérateur\***  permet à un objet pointeur intelligent d’agir comme s’il s’agissait de l’interface encapsulée réelle fois déréférencé.  
  
-   **operator ->** permet à un objet pointeur intelligent d’agir comme s’il s’agissait de l’interface encapsulée réelle fois déréférencé.  
  
-   **opérateur &** libère tout pointeur d’interface encapsulé en le remplaçant par **NULL**et retourne l’adresse du pointeur encapsulé. Ainsi, le pointeur intelligent à passer par adresse à une fonction qui a un **hors** paramètre par le biais duquel elle retourne un pointeur d’interface.  
  
-   **opérateur bool** permet à un objet pointeur intelligent à utiliser dans une expression conditionnelle. Cet opérateur retourne **true** si le pointeur n’est pas **NULL**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_ptr_t, classe](../cpp/com-ptr-t-class.md)