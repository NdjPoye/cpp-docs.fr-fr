---
title: Classe de CSimpleException | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException class
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5612d76a2351b9898b8ffe082844686d21fcd7a0
ms.lasthandoff: 02/24/2017

---
# <a name="csimpleexception-class"></a>CSimpleException (classe)
Cette classe est une classe de base pour les exceptions MFC critiques pour les ressources.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|Fournit le texte sur une erreur s’est produite.|  
  
## <a name="remarks"></a>Remarques  
 `CSimpleException`est la classe de base pour les exceptions MFC ressources critiques et gère la propriété et l’initialisation d’un message d’erreur. Les classes suivantes utilisent `CSimpleException` comme classe de base :  
  
|||  
|-|-|  
|[CMemoryException (classe)](../../mfc/reference/cmemoryexception-class.md)|Exception de mémoire insuffisante|  
|[Classe d’exception CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Requêtes pour une opération non prise en charge|  
|[CResourceException (classe)](../../mfc/reference/cresourceexception-class.md)|Ressources Windows introuvable ou ne peut pas être créé|  
|[CUserException (classe)](../../mfc/reference/cuserexception-class.md)|Exception qui indique qu’une ressource est introuvable.|  
|[CInvalidArgException (classe)](../../mfc/reference/cinvalidargexception-class.md)|Exception qui indique qu’un argument non valide|  
  
 Étant donné que `CSimpleException` est une classe de base abstraite, vous ne pouvez pas déclarer un `CSimpleException` directement l’objet. Au lieu de cela, vous devez déclarer les objets dérivés, tels que ceux dans le tableau précédent. Si vous déclarez votre propre classe dérivée, utilisez les classes précédentes en tant que modèle.  
  
 Pour plus d’informations, consultez la [CException (classe)](../../mfc/reference/cexception-class.md) rubrique et [la gestion des exceptions (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h  
  
##  <a name="csimpleexception"></a>CSimpleException::CSimpleException  
 Constructeur.  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Paramètres  
 `bAutoDelete`  
 Spécifier **TRUE** si la mémoire pour le `CSimpleException` objet a été alloué sur le tas. Cela entraîne le `CSimpleException` objet doit être supprimé lorsque le **supprimer** fonction membre est appelée pour supprimer l’exception. Spécifier **FALSE** si le `CSimpleException` objet sur la pile ou est un objet global. Dans ce cas, le `CSimpleException` objet ne sera pas supprimé lorsque la **supprimer** la fonction membre est appelée.  
  
### <a name="remarks"></a>Notes  
 Vous devez normalement jamais d’appeler ce constructeur directement. Une fonction qui lève une exception doit créer une instance d’un `CException`-classe dérivée et appelle son constructeur, ou il doit utiliser l’une des MFC lever des fonctions, telles que [AfxThrowFileException](exception-processing.md#afxthrowfileexception), lever un type prédéfini.  
  
##  <a name="geterrormessage"></a>CSimpleException::GetErrorMessage  
 Appelez cette fonction membre pour fournir le texte sur une erreur s’est produite.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszError`  
 Pointeur vers une mémoire tampon qui reçoit un message d’erreur.  
  
 `nMaxError`  
 Le nombre maximal de caractères que peut contenir la mémoire tampon, y compris la **NULL** marque de fin.  
  
 `pnHelpContext`  
 L’adresse d’un **UINT** qui recevra l’ID de contexte d’aide. Si **NULL**, aucun ID n’est retourné.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 si aucune erreur de message texte est disponible.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CException (classe)](../../mfc/reference/cexception-class.md)   
 [Gestion des exceptions](../../mfc/exception-handling-in-mfc.md)




