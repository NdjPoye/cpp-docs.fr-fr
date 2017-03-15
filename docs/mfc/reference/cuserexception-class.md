---
title: Classe de CUserException | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [C++], stopping
- exceptions, throwing
- CUserException class
- errors [C++], trapping
- operations [C++]
- throwing exceptions, stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 23
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8548ffa7ad9032e174d650e210a70a29b0e3f19d
ms.lasthandoff: 02/24/2017

---
# <a name="cuserexception-class"></a>CUserException (classe)
Levée pour arrêter une opération d'utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>Remarques  
 Utilisez `CUserException` lorsque vous souhaitez utiliser le mécanisme d’exception/catch lève des exceptions propres à l’application. « Utilisateur » dans le nom de classe peut être interprétée comme « mon utilisateur fait quelque chose d’exceptionnel que je dois gérer. »  
  
 A `CUserException` est généralement levée après l’appel de la fonction globale `AfxMessageBox` pour avertir l’utilisateur qu’une opération a échoué. Lorsque vous écrivez un gestionnaire d’exceptions, gérer l’exception spécialement dans la mesure où l’utilisateur généralement a déjà été informé de l’échec. Le framework lève cette exception dans certains cas. Pour lever une `CUserException` alerter l’utilisateur et vous-même, puis appelez la fonction globale `AfxThrowUserException`.  
  
 Dans l’exemple ci-dessous, une fonction contenant des opérations qui échouent en avertit l’utilisateur et lève un `CUserException`. La fonction appelante intercepte l’exception et il traite :  
  
 [!code-cpp[NVC_MFCExceptions&#24;](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 Pour plus d’informations sur l’utilisation de `CUserException`, consultez l’article [la gestion des exceptions (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CException (classe)](../../mfc/reference/cexception-class.md)

