---
title: _com_ptr_t::QueryInterface | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs: C++
helpviewer_keywords: QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 21dffde38e58bb7c07a1a92421d3febe10cc1032
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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