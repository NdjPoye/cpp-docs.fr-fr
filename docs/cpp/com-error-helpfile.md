---
title: _com_error::HelpFile | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::HelpFile
dev_langs:
- C++
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
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
ms.openlocfilehash: 7e1e9ec8c7d6684bb7b244fd9ba6773b6f1460e1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile
**Section spécifique à Microsoft**  
  
 Appels **IErrorInfo::GetHelpFile** (fonction).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
_bstr_t HelpFile() const;  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le résultat de **IErrorInfo::GetHelpFile** pour le **IErrorInfo** enregistré dans le `_com_error` objet. Le BSTR résultant est encapsulé dans un objet `_bstr_t`. Si aucun **IErrorInfo** est enregistré, il retourne vide `_bstr_t`.  
  
## <a name="remarks"></a>Remarques  
 Tout échec lors de l’appel du **IErrorInfo::GetHelpFile** méthode est ignorée.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)
