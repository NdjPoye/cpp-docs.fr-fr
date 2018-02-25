---
title: raw_property_prefixes | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- raw_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9c38541d720a9b2bc857a4121c2d0e33ec4fc5b9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes
**Spécifique à C++**  
  
 Spécifie d'autres préfixes pour trois méthodes de propriété.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>Paramètres  
 `GetPrefix`  
 Préfixe à utiliser pour le **propget** méthodes.  
  
 `PutPrefix`  
 Préfixe à utiliser pour le **propput** méthodes.  
  
 `PutRefPrefix`  
 Préfixe à utiliser pour le **propputref** méthodes.  
  
## <a name="remarks"></a>Notes  
 Par défaut, de bas niveau **propget**, **propput**, et **propputref** méthodes sont exposées par les fonctions membres nommées avec les préfixes de **get_**, **put_**, et **putref_** respectivement. Ces préfixes sont compatibles avec les noms utilisés dans les fichiers d'en-tête générés par MIDL.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)