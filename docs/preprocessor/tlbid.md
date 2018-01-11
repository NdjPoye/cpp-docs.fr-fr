---
title: /TLBID | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tlbid
dev_langs: C++
helpviewer_keywords: tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 812b105fc02782b611b3f55061e448062dcd07c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="tlbid"></a>tlbid
**Spécifique à C++**  
  
 Permet de charger des bibliothèques autres que la bibliothèque de types principale.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
tlbid(number)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `number`  
 Numéro de la bibliothèque de types dans `filename`.  
  
## <a name="remarks"></a>Notes  
 Si plusieurs bibliothèques de types sont générées dans une même DLL, il est possible de charger des bibliothèques autres que la bibliothèque de types primaires à l'aide de `tlbid`.  
  
 Exemple :  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 équivaut à :  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)