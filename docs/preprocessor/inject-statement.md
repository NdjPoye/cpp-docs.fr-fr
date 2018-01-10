---
title: inject_statement | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: inject_statement
dev_langs: C++
helpviewer_keywords: inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d1ac68cae628f09c9511c4b86eac75da8dff6ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="injectstatement"></a>inject_statement
**Spécifique à C++**  
  
 Insère son argument en tant que texte source dans l’en-tête de bibliothèque de types.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
inject_statement("source_text")  
```  
  
#### <a name="parameters"></a>Paramètres  
 `source_text`  
 Texte source à insérer dans le fichier d'en-tête de bibliothèque de types.  
  
## <a name="remarks"></a>Notes  
 Le texte est placé au début de la déclaration d'espace de noms qui encapsule le contenu de la bibliothèque de types dans le fichier d'en-tête.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)