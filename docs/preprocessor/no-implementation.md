---
title: no_implementation | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_implementation
dev_langs: C++
helpviewer_keywords: no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5d4c378d1d64eefe5ae641d259aa502b7e4bcf32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="noimplementation"></a>no_implementation
**Spécifique à C++**  
  
 Supprime la génération de l'en-tête .tli, qui contient les implémentations des fonctions membres de wrapper.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
no_implementation  
```  
  
## <a name="remarks"></a>Remarques  
 Si cet attribut est spécifié, l'en-tête .tlh, avec les déclarations pour exposer les éléments de bibliothèque de types, sera généré sans instruction `#include` pour inclure le fichier d'en-tête .tli.  
  
 Cet attribut est utilisé conjointement avec [implementation_only](../preprocessor/implementation-only.md).  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)