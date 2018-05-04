---
title: _com_ptr_t::QueryInterface | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c046f1b1d14b7e7dbd44ca9f5f012e632efef6e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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
  
## <a name="remarks"></a>Notes  
 Appels **IUnknown::QueryInterface** sur le pointeur d’interface encapsulé avec l’objet **IID** et retourne le pointeur d’interface brut résultant dans `p`. Cette routine retourne l'objet `HRESULT` pour indiquer un succès ou un échec.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_ptr_t, classe](../cpp/com-ptr-t-class.md)