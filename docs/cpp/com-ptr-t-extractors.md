---
title: _com_ptr_t, extracteurs | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
dev_langs:
- C++
helpviewer_keywords:
- operator Interface&
- '* operator, with specific objects'
- operator&
- operator*
- -> operator, with specific objects
- '& operator, with specific objects'
- operator Interface*
- operator *
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 136afa55361ff25f9ad606886be938a00551393d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

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
  
-   **Interface d’opérateur\* ** retourne le pointeur d’interface encapsulé, qui peut être **NULL**.  
  
-   **operator Interface &** retourne une référence au pointeur d’interface encapsulé et émet une erreur si le pointeur est **NULL**.  
  
-   **opérateur\* ** permet à un objet pointeur intelligent d’agir comme s’il s’agissait de l’interface encapsulée réelle fois déréférencé.  
  
-   **operator ->** permet à un objet pointeur intelligent d’agir comme s’il s’agissait de l’interface encapsulée réelle fois déréférencé.  
  
-   **opérateur &** libère tout pointeur d’interface encapsulé en le remplaçant par **NULL**et retourne l’adresse du pointeur encapsulé. Ainsi, le pointeur intelligent à passer par adresse à une fonction qui a un **hors** paramètre par le biais duquel elle retourne un pointeur d’interface.  
  
-   **opérateur bool** permet à un objet pointeur intelligent à utiliser dans une expression conditionnelle. Cet opérateur retourne **true** si le pointeur n’est pas **NULL**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_ptr_t, classe](../cpp/com-ptr-t-class.md)
