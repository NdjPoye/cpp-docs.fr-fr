---
title: _com_ptr_t::Attach | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
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
ms.openlocfilehash: aa14a5fb0e54971e19de1b46317d768e7fc06a2e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtattach"></a>_com_ptr_t::Attach
**Section spécifique à Microsoft**  
  
 Encapsule un pointeur d'interface brut du type de ce pointeur intelligent.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void Attach(  
   Interface* pInterface   
) throw( );  
void Attach(  
   Interface* pInterface,  
   bool fAddRef   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pInterface`  
 Pointeur d'interface brut.  
  
 `fAddRef`  
 S’il s’agit **true**, puis `AddRef` est appelée. S’il s’agit **false**, le `_com_ptr_t` objet prend possession du pointeur d’interface brut sans appeler `AddRef`.  
  
## <a name="remarks"></a>Remarques  
  
-   **Joindre (**`pInterface`**)** `AddRef` n’est pas appelée.     La propriété de l'interface est passée à cet objet `_com_ptr_t`. **Version** est appelé pour décrémenter le décompte de références du pointeur précédemment encapsulé.  
  
-   **Joindre (** `pInterface` **,**`fAddRef`**)** si `fAddRef` est **true**, `AddRef` est appelé pour incrémenter la référence compteur pour le pointeur d’interface encapsulé.       Si `fAddRef` est **false**, cette `_com_ptr_t` objet prend possession du pointeur d’interface brut sans appeler `AddRef`. **Version** est appelé pour décrémenter le décompte de références du pointeur précédemment encapsulé.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_ptr_t, classe](../cpp/com-ptr-t-class.md)
