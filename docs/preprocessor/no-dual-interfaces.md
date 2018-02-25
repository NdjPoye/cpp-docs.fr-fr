---
title: no_dual_interfaces | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba20fcba43cc23dfce447d7e91955a43c28a6a31
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**Spécifique à C++**  
  
 Modifie la façon dont le compilateur génère des fonctions wrapper pour les méthodes d'interface double.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
no_dual_interfaces  
```  
  
## <a name="remarks"></a>Notes  
 Normalement, le wrapper appelle la méthode via la table de fonctions virtuelles pour l'interface. Avec `no_dual_interfaces`, le wrapper appelle à la place **IDispatch::Invoke** pour appeler la méthode.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)