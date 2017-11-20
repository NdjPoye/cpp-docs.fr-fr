---
title: _com_error::description | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::Description
dev_langs: C++
helpviewer_keywords: Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c4bf868fd548cc7e0c72559f3754d7e1a035cfa5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="comerrordescription"></a>_com_error::Description
**Section spécifique à Microsoft**  
  
 Appels **IErrorInfo::GetDescription** (fonction).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le résultat de **IErrorInfo::GetDescription** pour le **IErrorInfo** enregistré dans le `_com_error` objet. Le `BSTR` résultant est encapsulé dans un objet `_bstr_t`. Si aucun **IErrorInfo** est enregistré, il retourne vide `_bstr_t`.  
  
## <a name="remarks"></a>Remarques  
 Appelle le **IErrorInfo::GetDescription** fonction et récupère **IErrorInfo** enregistré dans le `_com_error` objet. Tout échec lors de l’appel du **IErrorInfo::GetDescription** méthode est ignorée.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)