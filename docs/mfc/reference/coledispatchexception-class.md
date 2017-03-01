---
title: COleDispatchException classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDispatchException
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchException class
- Automation, exceptions
- exceptions, OLE
- OLE exceptions, to IDispatch interface
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
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
ms.openlocfilehash: 0071e57b6c8f6bec73712186e8ff8baa9bfcc165
ms.lasthandoff: 02/24/2017

---
# <a name="coledispatchexception-class"></a>COleDispatchException (classe)
Gère les exceptions propres à l'interface `IDispatch` OLE, qui est une partie fondamentale d'OLE automation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleDispatchException : public CException  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|Contexte d’aide pour l’erreur.|  
|[COleDispatchException::m_strDescription](#m_strdescription)|Description d’erreur.|  
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|Aide du fichier à utiliser avec `m_dwHelpContext`.|  
|[COleDispatchException::m_strSource](#m_strsource)|Application qui a généré l’exception.|  
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-code d’erreur spécifique.|  
  
## <a name="remarks"></a>Remarques  
 Comme les autres classes d’exceptions dérivées de la `CException` classe de base `COleDispatchException` peut être utilisé avec le **lever**, `THROW_LAST`, **essayez**, **CATCH**, `AND_CATCH`, et `END_CATCH` macros.  
  
 En général, vous devez appeler [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) de créer et de lever une `COleDispatchException` objet.  
  
 Pour plus d’informations sur les exceptions, consultez les articles [la gestion des exceptions (MFC)](../../mfc/exception-handling-in-mfc.md) et [Exceptions : Exceptions OLE](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleDispatchException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdisp.h  
  
##  <a name="a-namemdwhelpcontexta--coledispatchexceptionmdwhelpcontext"></a><a name="m_dwhelpcontext"></a>COleDispatchException::m_dwHelpContext  
 Identifie le contexte d’aide dans l’aide de votre application (. Fichier (HLP).  
  
```  
DWORD m_dwHelpContext;  
```  
  
### <a name="remarks"></a>Remarques  
 Ce membre est défini par la fonction [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) lorsqu’une exception est levée.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="a-namemstrdescriptiona--coledispatchexceptionmstrdescription"></a><a name="m_strdescription"></a>COleDispatchException::m_strDescription  
 Contient une description d’erreur, par exemple « Disque plein ».  
  
```  
CString m_strDescription;  
```  
  
### <a name="remarks"></a>Remarques  
 Ce membre est défini par la fonction [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) lorsqu’une exception est levée.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="a-namemstrhelpfilea--coledispatchexceptionmstrhelpfile"></a><a name="m_strhelpfile"></a>COleDispatchException::m_strHelpFile  
 L’infrastructure complète de cette chaîne par le nom du fichier d’aide de l’application.  
  
```  
CString m_strHelpFile;  
```  
  
##  <a name="a-namemstrsourcea--coledispatchexceptionmstrsource"></a><a name="m_strsource"></a>COleDispatchException::m_strSource  
 L’infrastructure complète de cette chaîne avec le nom de l’application qui a généré l’exception.  
  
```  
CString m_strSource;  
```  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="a-namemwcodea--coledispatchexceptionmwcode"></a><a name="m_wcode"></a>COleDispatchException::m_wCode  
 Contient un code d’erreur spécifique à votre application.  
  
```  
WORD m_wCode;  
```  
  
### <a name="remarks"></a>Notes  
 Ce membre est défini par la fonction [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) lorsqu’une exception est levée.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC CALCDRIV](../../visual-cpp-samples.md)   
 [CException (classe)](../../mfc/reference/cexception-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)   
 [COleException (classe)](../../mfc/reference/coleexception-class.md)

