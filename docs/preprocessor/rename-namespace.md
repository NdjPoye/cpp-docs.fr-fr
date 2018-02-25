---
title: rename_namespace | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37b2c01479cb489f7ed573f55a48f5807161bf63
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="renamenamespace"></a>rename_namespace
**Spécifique à C++**  
  
 Renomme l'espace de noms qui contient le contenu de la bibliothèque de types.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
rename_namespace("NewName")  
```  
  
#### <a name="parameters"></a>Paramètres  
 `NewName`  
 Nom du nouvel espace de noms.  
  
## <a name="remarks"></a>Notes  
 Il accepte un argument unique, *NewName*, qui spécifie le nouveau nom de l’espace de noms.  
  
 Pour supprimer l’espace de noms, utilisez la [no_namespace](../preprocessor/no-namespace.md) d’attribut à la place.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)