---
title: raw_method_prefix | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_method_prefix
dev_langs: C++
helpviewer_keywords: raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f140bf7d65f620552dea9f2d25f4ae472139b98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="rawmethodprefix"></a>raw_method_prefix
**Spécifique à C++**  
  
 Spécifie un préfixe différent pour éviter les collisions de noms.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Prefix`  
 Le préfixe à utiliser.  
  
## <a name="remarks"></a>Notes  
 Propriétés de bas niveau et les méthodes sont exposées par les fonctions membres nommées avec un préfixe par défaut de **raw_** afin d’éviter les collisions de noms avec les principales fonctions membres de gestion des erreurs.  
  
> [!NOTE]
>  Les effets de la `raw_method_prefix` attribut n’est pas modifié par la présence de la [raw_interfaces_only](#_predir_raw_interfaces_only) attribut. `raw_method_prefix` a toujours la priorité sur `raw_interfaces_only` pour spécifier un préfixe. Si les deux attributs sont utilisés dans la même instruction `#import`, le préfixe spécifié par l'attribut `raw_method_prefix` est utilisé.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)