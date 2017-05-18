---
title: Classe de CMemoryException | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException class
- memory exceptions
- exceptions, memory type
- C++ exception handling, memory
- memory, exception handling
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 87be1b16d546791d24bbffa62207ec9ccb350139
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmemoryexception-class"></a>CMemoryException (classe)
Représente une condition d'exception liée à une insuffisance de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMemoryException::CMemoryException](#cmemoryexception)|Construit un objet `CMemoryException`.|  
  
## <a name="remarks"></a>Remarques  
 Sans qualification supplémentaire est nécessaire ou possible. Mémoire des exceptions sont levées automatiquement par **nouveau**. Si vous écrivez vos propres fonctions de mémoire, à l’aide `malloc`, par exemple, vous êtes responsable de la lever des exceptions de mémoire.  
  
 Pour plus d’informations sur `CMemoryException`, consultez l’article [la gestion des exceptions (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h  
  
##  <a name="cmemoryexception"></a>CMemoryException::CMemoryException  
 Construit un objet `CMemoryException`.  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>Remarques  
 N’utilisez pas ce constructeur directement, mais plutôt appeler la fonction globale [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Cette fonction globale peut réussir dans une situation de mémoire insuffisante, car elle construit l’objet d’exception de mémoire précédemment alloué. Pour plus d’informations sur le traitement des exceptions, consultez l’article [exceptions](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CException (classe)](cexception-class.md)   
 [Graphique de la hiérarchie](../hierarchy-chart.md)




