---
title: "Erreur irrécupérable C1104 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1104
dev_langs: C++
helpviewer_keywords: C1104
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec6f6f7df6187da19b65c399def08be2a021c482
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1104"></a>Erreur irrécupérable C1104
erreur irrécupérable lors de l’importation de libid : 'message'  
  
 Le compilateur a détecté un problème d’importation d’une bibliothèque de types.  Par exemple, vous ne pouvez pas spécifier une bibliothèque de types avec libid et spécifier également `no_registry`.  
  
 Pour plus d’informations, consultez [Directive #import](../../preprocessor/hash-import-directive-cpp.md).  
  
 L’exemple suivant génère l’erreur C1104 :  
  
```  
// C1104.cpp  
#import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104  
```