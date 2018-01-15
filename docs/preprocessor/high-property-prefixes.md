---
title: high_property_prefixes | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: high_property_prefixes
dev_langs: C++
helpviewer_keywords: high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed37cdc51c5e08899786ce82a9c3e5e3224f9f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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