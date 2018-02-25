---
title: raw_dispinterfaces | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- raw_dispinterfaces
dev_langs:
- C++
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9c20cc7cab6c85f203bc83523229f50749332f3d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**Spécifique à C++**  
  
 Indique au compilateur de générer des fonctions wrapper de bas niveau pour les méthodes dispinterface et les propriétés qui appellent **IDispatch::Invoke** et retourner le `HRESULT` code d’erreur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
raw_dispinterfaces  
```  
  
## <a name="remarks"></a>Notes  
 Si cet attribut n'est pas spécifié, seuls sont générés les wrappers de niveau supérieur, qui lèvent des exceptions C++ en cas d'échec.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)