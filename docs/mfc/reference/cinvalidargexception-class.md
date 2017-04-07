---
title: Classe de CInvalidArgException | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
dev_langs:
- C++
helpviewer_keywords:
- CInvalidArgException class
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 4091c0e8a35320482eba193c89c90982c7e4fca9
ms.lasthandoff: 02/24/2017

---
# <a name="cinvalidargexception-class"></a>CInvalidArgException (classe)
Cette classe représente une condition d’exception d’argument non valide.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CInvalidArgException : public CSimpleException  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|Constructeur.|  
  
## <a name="remarks"></a>Remarques  
 Un `CInvalidArgException` objet représente une condition d’exception argument non valide.  
  
 Pour plus d’informations sur la gestion des exceptions, consultez la [CException (classe)](../../mfc/reference/cexception-class.md) rubrique et [la gestion des exceptions (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CInvalidArgException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h  
  
##  <a name="cinvalidargexception"></a>CInvalidArgException::CInvalidArgException  
 Constructeur.  
  
```  
CInvalidArgException();
```  
  
### <a name="remarks"></a>Notes  
 N’utilisez pas ce constructeur directement. Appelez la fonction globale **AfxThrowInvalidArgException**.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CSimpleException (classe)](../../mfc/reference/csimpleexception-class.md)

