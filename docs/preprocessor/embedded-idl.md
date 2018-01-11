---
title: embedded_idl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: embedded_idl
dev_langs: C++
helpviewer_keywords: embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0a83b635dc7d408b6296c0407984ddfb9a9f3659
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="embeddedidl"></a>embedded_idl
**Spécifique à C++**  
  
 Indique que la bibliothèque de types est écrite dans le fichier .tlh et que le code généré par attributs est conservé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
embedded_idl[("param")]  
```  
  
#### <a name="parameters"></a>Paramètres  
 `param`  
 Peut avoir l'une des deux valeurs suivantes :  
  
-   emitidl : les informations de type importées à partir du typelib seront présentes dans le fichier IDL généré pour le projet avec attributs.  Il s'agit de la valeur par défaut qui sera appliquée si vous ne spécifiez pas de paramètre pour `embedded_idl`.  
  
-   no_emitidl : les informations de type importées à partir du typelib ne seront pas présentes dans le fichier IDL généré pour le projet avec attributs.  
  
## <a name="example"></a>Exemple  
  
```  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## <a name="remarks"></a>Notes  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)