---
title: _com_error::ErrorMessage | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::ErrorMessage
dev_langs: C++
helpviewer_keywords: ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8690c23acf6e42d355cf122f59f54e19cc36d66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
  
## <a name="remarks"></a>Notes  
 Récupère le texte de message système approprié pour le `HRESULT` enregistré dans l'objet `_com_error`. Le texte du message système est obtenu en appelant Win32 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) (fonction). La chaîne retournée est allouée par l'API `FormatMessage` et elle est libérée lorsque l'objet `_com_error` est détruit.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)