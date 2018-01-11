---
title: raw_native_types | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_native_types
dev_langs: C++
helpviewer_keywords: raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cdd40f219115adf43f0681d8719aceb9ed9d9fd2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="rawnativetypes"></a>raw_native_types
**Spécifique à C++**  
  
 Désactive l'utilisation des classes de prise en charge COM dans les fonctions wrapper de haut niveau et force l'utilisation de types de données de bas niveau à la place.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
raw_native_types  
```  
  
## <a name="remarks"></a>Notes  
 Par défaut, les méthodes de gestion des erreurs de haut niveau utilisent les classes de prise en charge COM [_bstr_t](../cpp/bstr-t-class.md) et [_variant_t](../cpp/variant-t-class.md) à la place de la `BSTR` et **VARIANT** des types de données et pointeurs d’interface COM bruts. Ces classes encapsulent les détails de l'allocation et de la libération du stockage de mémoire pour ces types de données, et simplifient considérablement le casting de type et les opérations de conversion.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)