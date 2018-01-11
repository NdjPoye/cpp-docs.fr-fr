---
title: Platform::changedstateexception, classe | Documents Microsoft
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::ChangedStateException
- VCCORLIB/Platform::ChangedStateException::ChangedStateException
dev_langs: C++
helpviewer_keywords: Platform::ChangedStateException
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e874cb1ca3db5741d2974499c53e23816e204186
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="platformchangedstateexception-class"></a>Platform::ChangedStateException, classe
Exception levée lorsque l'état interne d'un objet a changé, ce qui entraîne l'invalidation des résultats de la méthode.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>Notes  
 Par exemple, cette exception est levée lorsque les méthodes d'un itérateur de collection ou d'une vue de collection sont appelées après la modification d'une collection parente, invalidant ainsi les résultats de la méthode.  
  
 Pour plus d'informations, consultez la classe [COMException](../cppcx/platform-comexception-class.md) .  
  
### <a name="requirements"></a>Configuration requise  
 **Minimum pris en charge le client :** Windows 8  
  
 **Minimum de serveur pris en charge :** Windows Server 2012  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## <a name="see-also"></a>Voir aussi  
 [Platform::COMException, classe](../cppcx/platform-comexception-class.md)