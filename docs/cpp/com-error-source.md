---
title: _com_error::source | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::Source
dev_langs:
- C++
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: 6
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 848d402e83c09ff85537115437c8a190d160f984
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorsource"></a>_com_error::Source
**Section spécifique à Microsoft**  
  
 Appels **IErrorInfo::GetSource** (fonction).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le résultat de **IErrorInfo::GetSource** pour le **IErrorInfo** enregistré dans le `_com_error` objet. Le BSTR résultant est encapsulé dans un objet `_bstr_t`. Si aucun **IErrorInfo** est enregistré, il retourne vide `_bstr_t`.  
  
## <a name="remarks"></a>Remarques  
 Tout échec lors de l’appel du **IErrorInfo::GetSource** méthode est ignorée.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)
