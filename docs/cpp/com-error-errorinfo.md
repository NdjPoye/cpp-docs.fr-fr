---
title: _com_error::ErrorInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 642078d84f72a553e9b2407b279265a3a7e77522
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Section spécifique à Microsoft**  
  
 Récupère le **IErrorInfo** objet passé au constructeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Brutes **IErrorInfo** élément passé au constructeur.  
  
## <a name="remarks"></a>Notes  
 Récupère l’encapsulé **IErrorInfo** d’élément dans un `_com_error` objet, ou **NULL** si aucun **IErrorInfo** article est enregistré. L’appelant doit appeler **version** sur l’objet retourné lors de la fin de l’utiliser.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)