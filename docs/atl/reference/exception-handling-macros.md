---
title: Macros des exceptions | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9d99551d8dbe116c9f4fafeb9602e471839003a7
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="exception-handling-macros"></a>Macros de gestion des exceptions
Ces macros prennent en charge la gestion des exceptions.  
  
|||  
|-|-|  
|[_ATLCATCH](#_atlcatch)|Instructions permettant de gérer les erreurs qui se produisent dans le type `_ATLTRY`.|  
|[_ATLCATCHALL](#_atlcatchall)|Instructions permettant de gérer les erreurs qui se produisent dans le type `_ATLTRY`.|  
|[_ATLTRY](#_atltry)|Marque une section de code protégée où une erreur peut éventuellement se produire.|  
  
##  <a name="_atlcatch"></a>_ATLCATCH  
 Instructions permettant de gérer les erreurs qui se produisent dans le type `_ATLTRY`.  
  
```
_ATLCATCH(e)
```  
  
### <a name="parameters"></a>Paramètres  
 *e*  
 Exception à intercepter.  
  
### <a name="remarks"></a>Notes  
 Utilisé conjointement avec `_ATLTRY`. Est résolu en C++ [catch (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) pour gérer un type donné des exceptions C++.  
  
##  <a name="_atlcatchall"></a>_ATLCATCHALL  
 Instructions permettant de gérer les erreurs qui se produisent dans le type `_ATLTRY`.  
  
```
_ATLCATCHALL
```  
  
### <a name="remarks"></a>Notes  
 Utilisé conjointement avec `_ATLTRY`. Est résolu en C++ [catch (...) ](../../cpp/try-throw-and-catch-statements-cpp.md) pour la gestion de tous les types d’exceptions C++.  
  
##  <a name="_atltry"></a>_ATLTRY  
 Marque une section de code protégée où une erreur peut éventuellement se produire.  
  
```
_ATLTRY
```  
  
### <a name="remarks"></a>Notes  
 Utilisé conjointement avec [_ATLCATCH](#_atlcatch) ou [_ATLCATCHALL](#_atlcatchall). Correspond au symbole C++ [essayez](../../cpp/try-throw-and-catch-statements-cpp.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)

