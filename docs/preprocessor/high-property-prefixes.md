---
title: high_property_prefixes | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- high_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7df4ef6cded98c19ead86160aa772e349ebfd37
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="highpropertyprefixes"></a>high_property_prefixes
**Spécifique à C++**  
  
 Spécifie d'autres préfixes pour trois méthodes de propriété.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>Paramètres  
 `GetPrefix`  
 Préfixe à utiliser pour le **propget** méthodes.  
  
 `PutPrefix`  
 Préfixe à utiliser pour le **propput** méthodes.  
  
 `PutRefPrefix`  
 Préfixe à utiliser pour le **propputref** méthodes.  
  
## <a name="remarks"></a>Notes  
 Par défaut, la gestion des erreurs principales **propget**, **propput**, et **propputref** méthodes sont exposées par les fonctions membres nommées avec les préfixes **obtenir** , `Put`, et **PutRef**, respectivement.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)