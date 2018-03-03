---
title: NOM (C/C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- name
dev_langs:
- C++
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33e81f63e7647cbdbdc89b37ffdcb309b79e9340
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="name-cc"></a>NAME (C/C++)
Spécifie un nom pour le fichier de sortie principal.  
  
```  
NAME [application][BASE=address]  
```  
  
## <a name="remarks"></a>Notes  
 Vous pouvez spécifier un nom de fichier de sortie est le [/OUT](../../build/reference/out-output-file-name.md) option de l’éditeur de liens et pour définir l’adresse de base d’une manière équivalente est le [/BASE](../../build/reference/base-base-address.md) option de l’éditeur de liens. Si les deux sont spécifiées, les remplacements **nom**.  
  
 Si vous générez une DLL, le nom n’affecte que le nom de la DLL.  
  
## <a name="see-also"></a>Voir aussi  
 [Règles s’appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)