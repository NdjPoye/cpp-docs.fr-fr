---
title: _com_error::HelpContext | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::HelpContext
dev_langs:
- C++
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2dbdd52b311a35d390a61a0601a63c1b680f79b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Section spécifique à Microsoft**  
  
 Appels **IErrorInfo::GetHelpContext** (fonction).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le résultat de **IErrorInfo::GetHelpContext** pour le **IErrorInfo** enregistré dans le `_com_error` objet. Si aucun **IErrorInfo** objet est enregistré, elle retourne une valeur zéro.  
  
## <a name="remarks"></a>Notes  
 Tout échec lors de l’appel du **IErrorInfo::GetHelpContext** méthode est ignorée.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)