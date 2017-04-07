---
title: Classe de CAtlException | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
dev_langs:
- C++
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 30c9235f16581c86ab5612522909dc366b1ce17e
ms.lasthandoff: 02/24/2017

---
# <a name="catlexception-class"></a>CAtlException (classe)
Cette classe définit une exception ATL.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAtlException
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlException::CAtlException](#catlexception)|Constructeur.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlException::operator HRESULT](#operator_hresult)|Convertit l’objet en cours à une valeur HRESULT.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlException::m_hr](#m_hr)|La variable de type HRESULT créé par l’objet et permet de stocker la condition d’erreur.|  
  
## <a name="remarks"></a>Remarques  
 Un `CAtlException` objet représente une condition d’exception associée à une opération de ATL. La `CAtlException` classe inclut une donnée membre publique qui stocke le code d’état indiquant la raison de l’exception et un opérateur de conversion qui vous permet de traiter l’exception comme s’il s’agissait d’une valeur HRESULT.  
  
 En général, vous appellerez `AtlThrow` au lieu de créer un `CAtlException` directement l’objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlexcept.h  
  
##  <a name="catlexception"></a>CAtlException::CAtlException  
 Constructeur.  
  
```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `hr`  
 Le `HRESULT` code d’erreur.  
  
##  <a name="operator_hresult"></a>CAtlException::operator HRESULT 
 Convertit l’objet en cours à une valeur HRESULT.  
  
```  
operator HRESULT() const throw ();
```  
  
##  <a name="m_hr"></a>CAtlException::m_hr  
 Le `HRESULT` membre de données.  
  
```
HRESULT m_hr;
```  
  
### <a name="remarks"></a>Remarques  
 Le membre de données qui stocke la condition d’erreur. La valeur HRESULT est définie par le constructeur, [CAtlException::CAtlException](#catlexception).  
  
## <a name="see-also"></a>Voir aussi  
 [AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

