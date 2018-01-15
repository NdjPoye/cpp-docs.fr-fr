---
title: no_namespace | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_namespace
dev_langs: C++
helpviewer_keywords: no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b83e60aca7ea0e39ba67834ad1def0896dcdc07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nonamespace"></a>no_namespace
**Spécifique à C++**  
  
 Indique que le nom de l'espace de noms n'est pas généré par le compilateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>Notes  
 Le contenu de la bibliothèque de types dans le fichier d'en-tête `#import` est normalement défini dans un espace de noms. Le nom de l’espace de noms est spécifié dans le **bibliothèque** instruction du fichier IDL d’origine. Si l'attribut `no_namespace` est spécifié, cet espace de noms n'est pas généré par le compilateur.  
  
 Si vous souhaitez utiliser un nom d’espace de noms différent, puis utiliser le [rename_namespace](../preprocessor/rename-namespace.md) d’attribut à la place.  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)