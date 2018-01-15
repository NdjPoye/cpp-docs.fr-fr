---
title: rename_namespace | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: rename_namespace
dev_langs: C++
helpviewer_keywords: rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 856762f9582f4a91275c29d49c5065e8436cc719
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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