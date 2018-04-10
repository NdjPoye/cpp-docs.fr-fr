---
title: VERSION (C/C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VERSION
dev_langs:
- C++
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63ea65a8e3732ee17cc30b3382aa7ebc56e48f59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="version-cc"></a>VERSION (C/C++)
Indique à LINK d’insérer un nombre dans l’en-tête du fichier .exe ou DLL.  
  
```  
VERSION major[.minor]  
```  
  
## <a name="remarks"></a>Notes  
 Le *majeure* et *secondaire* arguments sont des nombres décimaux compris entre 0 et 65 535. La valeur par défaut est la version 0.0.  
  
 Vous pouvez spécifier un numéro de version est avec le [les informations de Version](../../build/reference/version-version-information.md) (/ VERSION) option.  
  
## <a name="see-also"></a>Voir aussi  
 [Règles s’appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)