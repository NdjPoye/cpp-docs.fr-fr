---
title: _com_error::ErrorInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::ErrorInfo
dev_langs: C++
helpviewer_keywords: ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3e968a3b9814aeec898d4e157781b58c40a87e25
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
  
## <a name="remarks"></a>Remarques  
 Récupère l’encapsulé **IErrorInfo** d’élément dans un `_com_error` objet, ou **NULL** si aucun **IErrorInfo** article est enregistré. L’appelant doit appeler **version** sur l’objet retourné lors de la fin de l’utiliser.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)