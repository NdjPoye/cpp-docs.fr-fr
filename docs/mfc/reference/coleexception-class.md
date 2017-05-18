---
title: Classe de COleException | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
dev_langs:
- C++
helpviewer_keywords:
- COleException class
- exceptions, OLE
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 059c92c8dc8796cf103cc02533ba5f3526720249
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="coleexception-class"></a>COleException (classe)
Représente une condition d'exception liée à une opération OLE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleException::Process](#process)|Se traduit par une exception interceptée dans un code de retour OLE.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|Contient le code d’état qui indique la raison de l’exception.|  
  
## <a name="remarks"></a>Notes  
 La `COleException` classe inclut une donnée membre publique qui conserve le code d’état indiquant la raison de l’exception.  
  
 En général, vous ne devez pas créer un `COleException` de l’objet directement ; au lieu de cela, vous devez appeler [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Pour plus d’informations sur les exceptions, consultez les articles [la gestion des exceptions (MFC)](../../mfc/exception-handling-in-mfc.md) et [Exceptions : Exceptions OLE](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdisp.h  
  
##  <a name="m_sc"></a>COleException::m_sc  
 Ce membre de données contient le code d’état OLE qui indique la raison de l’exception.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>Remarques  
 La valeur de cette variable est définie par [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Pour plus d’informations sur `SCODE`, consultez [Structure des Codes d’erreur COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCOleContainer&#22;](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>COleException::Process  
 Appelez le **processus** fonction membre pour convertir une exception interceptée dans un code d’état OLE.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>Paramètres  
 *pAnyException*  
 Pointeur vers une exception interceptée.  
  
### <a name="return-value"></a>Valeur de retour  
 Un code d’état OLE.  
  
### <a name="remarks"></a>Remarques  
  
> [!NOTE]
>  Cette fonction est **statique**.  
  
 Pour plus d’informations sur `SCODE`, consultez [Structure des Codes d’erreur COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC CALCDRIV](../../visual-cpp-samples.md)   
 [CException (classe)](../../mfc/reference/cexception-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




