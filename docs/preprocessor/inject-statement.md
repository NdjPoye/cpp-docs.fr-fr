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
ms.openlocfilehash: bb3bd5c1456daad18d374e5befa6936a0535dd38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
  
## <a name="remarks"></a>Remarques  
 Le texte est placé au début de la déclaration d'espace de noms qui encapsule le contenu de la bibliothèque de types dans le fichier d'en-tête.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)