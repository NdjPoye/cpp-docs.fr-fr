---
title: _com_error::ErrorMessage | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- ErrorMessage method
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
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
ms.openlocfilehash: 01f244a07e46c70cbd4810af666f55dc899e5c3a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage
**Section spécifique à Microsoft**  
  
 Récupère le message de chaîne pour `HRESULT` stocké dans l'objet `_com_error`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le message de chaîne pour le `HRESULT` stocké dans l'objet `_com_error`. Si le `HRESULT` est 16 bits mappée [wCode](../cpp/com-error-wcode.md), puis un message générique «`IDispatch error #<wCode>`» est retournée. Si aucun message n'est trouvé, un message générique « `Unknown error #<hresult>` » est retourné. La chaîne retournée est soit une chaîne Unicode ou multioctets, selon l’état de la **_UNICODE** (macro).  
  
## <a name="remarks"></a>Remarques  
 Récupère le texte de message système approprié pour le `HRESULT` enregistré dans l'objet `_com_error`. Le texte du message système est obtenu en appelant Win32 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) (fonction). La chaîne retournée est allouée par l'API `FormatMessage` et elle est libérée lorsque l'objet `_com_error` est détruit.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)
