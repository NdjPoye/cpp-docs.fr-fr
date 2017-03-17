---
title: "Classe d’exception CNotSupportedException | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs:
- C++
helpviewer_keywords:
- CNotSupportedException class
- unsupported features
- exceptions, not supported
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: 20
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
ms.openlocfilehash: 6cb66448d0dadaf1f70c3606bc1b9027bd217a38
ms.lasthandoff: 02/24/2017

---
# <a name="cnotsupportedexception-class"></a>Classe d’exception CNotSupportedException
Représente une exception qui est le résultat d’une requête portant sur une fonctionnalité non prise en charge.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Construit un objet `CNotSupportedException`.|  
  
## <a name="remarks"></a>Notes  
 Sans qualification supplémentaire est nécessaire ou possible.  
  
 Pour plus d’informations sur l’utilisation de `CNotSupportedException`, consultez l’article [la gestion des exceptions (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h  
  
##  <a name="cnotsupportedexception"></a>CNotSupportedException::CNotSupportedException  
 Construit un objet `CNotSupportedException`.  
  
```  
CNotSupportedException();
```  
  
### <a name="remarks"></a>Remarques  
 N’utilisez pas ce constructeur directement, mais plutôt appeler la fonction globale [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). Pour plus d’informations sur le traitement des exceptions, consultez l’article [la gestion des exceptions dans MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CException (classe)](cexception-class.md)   
 [Graphique de la hiérarchie](../hierarchy-chart.md)



