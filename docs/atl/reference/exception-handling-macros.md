---
title: "Macros d’exceptions | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
dev_langs: C++
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 424a65c44d7bb22d1fef6e21e1892967ecd3e9b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="exception-handling-macros"></a>Macros de gestion des exceptions
Ces macros prennent en charge la gestion des exceptions.  
  
|||  
|-|-|  
|[_ATLCATCH](#_atlcatch)|Instructions permettant de gérer les erreurs qui se produisent dans le type `_ATLTRY`.|  
|[_ATLCATCHALL](#_atlcatchall)|Instructions permettant de gérer les erreurs qui se produisent dans le type `_ATLTRY`.|  
|[_ATLTRY](#_atltry)|Marque une section de code protégé où une erreur peut éventuellement se produire.|  
  
## <a name="requirements"></a>Configuration requise :
**En-tête :** atldef.h

##  <a name="_atlcatch"></a>_ATLCATCH  
 Instructions permettant de gérer les erreurs qui se produisent dans le type `_ATLTRY`.  
  
```
_ATLCATCH(e)
```  
  
### <a name="parameters"></a>Paramètres  
 *e*  
 Exception à intercepter.  
  
### <a name="remarks"></a>Notes  
 Utilisée conjointement avec `_ATLTRY`. Est résolu en C++ [catch (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) pour la gestion d’un type donné d’exceptions C++.  
  
##  <a name="_atlcatchall"></a>_ATLCATCHALL  
 Instructions permettant de gérer les erreurs qui se produisent dans le type `_ATLTRY`.  
  
```
_ATLCATCHALL
```  
  
### <a name="remarks"></a>Notes  
 Utilisée conjointement avec `_ATLTRY`. Est résolu en C++ [catch (...) ](../../cpp/try-throw-and-catch-statements-cpp.md) pour la gestion de tous les types d’exceptions C++.  
  
##  <a name="_atltry"></a>_ATLTRY  
 Marque une section de code protégé où une erreur peut éventuellement se produire.  
  
```
_ATLTRY
```  
  
### <a name="remarks"></a>Notes  
 Utilisée conjointement avec [_ATLCATCH](#_atlcatch) ou [_ATLCATCHALL](#_atlcatchall). Correspond au symbole C++ [essayez](../../cpp/try-throw-and-catch-statements-cpp.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)
