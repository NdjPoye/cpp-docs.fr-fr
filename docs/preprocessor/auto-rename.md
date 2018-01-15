---
title: auto_rename | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: auto_rename
dev_langs: C++
helpviewer_keywords: auto_rename attribute
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76062a4a1eb44019b8677692ba895c5dcf9850cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="autorename"></a>auto_rename
**Spécifique à C++**  
  
 Renomme des mots réservés C++ en ajoutant deux traits de soulignement (__) au nom de variable pour résoudre les conflits potentiels entre les noms.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
auto_rename  
```  
  
## <a name="remarks"></a>Notes  
 Cet attribut est utilisé lors de l'importation d'une bibliothèque de types qui utilise un ou plusieurs mots réservés C++ (mots clés ou macros) comme noms de variables.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)