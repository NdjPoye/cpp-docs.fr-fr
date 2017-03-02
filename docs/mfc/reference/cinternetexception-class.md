---
title: Classe de la classe CInternetException | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetException
dev_langs:
- C++
helpviewer_keywords:
- exception handling, Internet operations
- exceptions, Internet
- CInternetException class
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a128095cfc443f0ea8de4cb4028b903929a83f47
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetexception-class"></a>Classe de la classe CInternetException
Représente une condition d'exception liée à une opération Internet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CInternetException : public CException  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetException::CInternetException](#cinternetexception)|Construit un objet `CInternetException`.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetException::m_dwContext](#m_dwcontext)|La valeur de contexte associée à l’opération qui a provoqué l’exception.|  
|[CInternetException::m_dwError](#m_dwerror)|L’erreur qui a provoqué l’exception.|  
  
## <a name="remarks"></a>Remarques  
 La `CInternetException` classe inclut deux membres de données publics : un conserve le code d’erreur associé à l’exception, et l’autre contient l’identificateur de contexte de l’application Internet associée à l’erreur.  
  
 Pour plus d’informations sur les identificateurs de contexte pour les applications Internet, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
  
##  <a name="a-namecinternetexceptiona--cinternetexceptioncinternetexception"></a><a name="cinternetexception"></a>CInternetException::CInternetException  
 Cette fonction membre est appelée quand un `CInternetException` objet est créé.  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwError`  
 L’erreur qui a provoqué l’exception.  
  
### <a name="remarks"></a>Notes  
 Pour lever une classe CInternetException, appelez la fonction globale MFC [AfxThrowInternetException](http://msdn.microsoft.com/library/c9645b10-9541-48b2-8b0c-94ca33fed3cb).  
  
##  <a name="a-namemdwcontexta--cinternetexceptionmdwcontext"></a><a name="m_dwcontext"></a>CInternetException::m_dwContext  
 La valeur de contexte associée à l’opération Internet connexe.  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>Notes  
 L’identificateur de contexte est spécifié à l’origine dans [CInternetSession](../../mfc/reference/cinternetsession-class.md) et passées par MFC [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- et [CInternetFile](../../mfc/reference/cinternetfile-class.md)-classes dérivées. Vous pouvez remplacer cette valeur par défaut et affecter l’un `dwContext` paramètre une valeur de votre choix. `dwContext`est associé à une opération de l’objet donné. `dwContext`identifie les informations d’état de l’opération retournées par [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
##  <a name="a-namemdwerrora--cinternetexceptionmdwerror"></a><a name="m_dwerror"></a>CInternetException::m_dwError  
 L’erreur qui a provoqué l’exception.  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>Remarques  
 Cette valeur d’erreur peut être un système de code d’erreur, trouvé dans WINERROR. H ou une valeur d’erreur de WININET. H.  
  
 Pour obtenir la liste des codes d’erreur Win32, consultez [Codes d’erreur](http://msdn.microsoft.com/library/windows/desktop/ms681381). Pour obtenir la liste des messages d’erreur spécifiques à Internet, consultez. Les deux rubriques se trouvent dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [CException (classe)](../../mfc/reference/cexception-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CException (classe)](../../mfc/reference/cexception-class.md)

