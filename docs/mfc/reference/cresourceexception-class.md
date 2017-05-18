---
title: Classe de CResourceException | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
dev_langs:
- C++
helpviewer_keywords:
- resource allocation exception
- resources [C++], allocating
- resource exceptions
- exceptions, resource
- CResourceException class
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2013a73f91687277df9dd1e6747aba2dd02a4346
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cresourceexception-class"></a>CResourceException (classe)
Générée lorsque Windows ne peut pas trouver ou allouer une ressource demandée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CResourceException : public CSimpleException  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CResourceException::CResourceException](#cresourceexception)|Construit un objet `CResourceException`.|  
  
## <a name="remarks"></a>Remarques  
 Sans qualification supplémentaire est nécessaire ou possible.  
  
 Pour plus d’informations sur l’utilisation de `CResourceException`, consultez l’article [la gestion des exceptions (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="cresourceexception"></a>CResourceException::CResourceException  
 Construit un objet `CResourceException`.  
  
```  
CResourceException();
```  
  
### <a name="remarks"></a>Remarques  
 N’utilisez pas ce constructeur directement, mais plutôt appeler la fonction globale [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). Pour plus d’informations sur les exceptions, consultez l’article [la gestion des exceptions dans MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CException (classe)](cexception-class.md)   
 [Graphique de la hiérarchie](../hierarchy-chart.md)



