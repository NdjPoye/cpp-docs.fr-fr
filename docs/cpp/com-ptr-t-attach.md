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
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d8b9eac88c9387c6aeedd140159bb24482c829dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
  
## <a name="remarks"></a>Notes  
  
-   **Joindre (**`pInterface`**)** `AddRef` n’est pas appelée. La propriété de l'interface est passée à cet objet `_com_ptr_t`. **Version** est appelé pour décrémenter le décompte de références du pointeur précédemment encapsulé.  
  
-   **Joindre (** `pInterface` **,**`fAddRef`**)** si `fAddRef` est **true**, `AddRef` est appelé pour incrémenter la référence compteur pour le pointeur d’interface encapsulé. Si `fAddRef` est **false**, cette `_com_ptr_t` objet prend possession du pointeur d’interface brut sans appeler `AddRef`. **Version** est appelé pour décrémenter le décompte de références du pointeur précédemment encapsulé.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_ptr_t, classe](../cpp/com-ptr-t-class.md)