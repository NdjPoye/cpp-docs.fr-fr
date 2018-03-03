---
title: SafeIntException, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeIntException Class
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException class
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 91f1c80273d0e1ed41ea86774c71fcbe8ad1bbf6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="safeintexception-class"></a>SafeIntException, classe
Le `SafeInt` classe utilise `SafeIntException` pour identifier la raison pour laquelle une opération mathématique ne peut pas être exécutée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class SafeIntException;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
 [SafeIntException::SafeIntException](../windows/safeintexception-safeintexception.md)  
 Crée un objet `SafeIntException`.  
  
## <a name="remarks"></a>Notes  
 Le [SafeInt, classe](../windows/safeint-class.md) est la seule classe qui utilise le `SafeIntException` classe.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [SafeIntException Class](../windows/safeintexception-class.md)  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** safeint.h  
  
 **Namespace :** msl::utilities  
  
## <a name="see-also"></a>Voir aussi  
 [Bibliothèque SafeInt](../windows/safeint-library.md)   
 [SafeInt, classe](../windows/safeint-class.md)