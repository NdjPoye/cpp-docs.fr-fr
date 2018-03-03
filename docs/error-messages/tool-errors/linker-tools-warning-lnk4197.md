---
title: "LNK4197 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1fadbf2ba5b18004f0e89142c88a68437842a92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4197"></a>Avertissement des outils Éditeur de liens LNK4197
exportation 'exportname' spécifié plusieurs fois ; à l’aide de la première spécification  
  
 Une exportation est spécifiée dans plusieurs et différentes façons. L’éditeur de liens utilise la première spécification et ignore le reste.  
  
 Si vous régénérez la bibliothèque Runtime C, vous pouvez ignorer ce message.  
  
 Si une exportation est spécifiée à la même manière que plusieurs fois, l’éditeur de liens émet un avertissement pas.  
  
 Par exemple, le contenu suivant d’un fichier .def peut causer cet avertissement :  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  La même exportation est spécifiée à la fois sur la ligne de commande (par export :) et dans le fichier .def  
  
2.  La même exportation est répertoriée deux fois dans le fichier .def avec des attributs différents.