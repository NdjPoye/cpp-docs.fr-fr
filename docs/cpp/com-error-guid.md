---
title: _com_error::GUID | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::GUID
dev_langs: C++
helpviewer_keywords: GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1165f53027c5b8a116f97cd2660c7ca12c9e7302
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorguid"></a>_com_error::GUID
**Section spécifique à Microsoft**  
  
 Appels **IErrorInfo::GetGUID** (fonction).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le résultat de **IErrorInfo::GetGUID** pour le **IErrorInfo** enregistré dans le `_com_error` objet. Si aucun **IErrorInfo** objet est enregistré, il retourne `GUID_NULL`.  
  
## <a name="remarks"></a>Notes  
 Tout échec lors de l’appel du **IErrorInfo::GetGUID** méthode est ignorée.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)