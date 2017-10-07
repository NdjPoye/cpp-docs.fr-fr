---
title: _com_ptr_t::QueryInterface | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6b5c8fb9ca1d628b178c19b677b90f17cc992373
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface
**Section spécifique à Microsoft**  
  
 Appelle le `QueryInterface` fonction membre de **IUnknown** sur le pointeur d’interface encapsulé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType*& p   
) throw ( );  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType** p  
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `iid`  
 **IID** d’un pointeur d’interface.  
  
 `p`  
 Pointeur d'interface brut.  
  
## <a name="remarks"></a>Remarques  
 Appels **IUnknown::QueryInterface** sur le pointeur d’interface encapsulé avec l’objet **IID** et retourne le pointeur d’interface brut résultant dans `p`. Cette routine retourne l'objet `HRESULT` pour indiquer un succès ou un échec.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_ptr_t, classe](../cpp/com-ptr-t-class.md)
