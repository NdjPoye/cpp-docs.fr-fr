---
title: processus | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8aa1ba2676ebbd04d1fc1a59d210d69efeab6658
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="process"></a>process
Spécifie que votre processus d'application managé doit comporter une seule copie d'une variable globale particulière, d'une variable membre static ou d'une variable locale static partagée par tous les domaines d'application du processus. Cela est principalement destinée à être utilisée lors de la compilation avec **/CLR : pure**, qui est désormais déconseillé et sera supprimé dans une future version du compilateur. Lors de la compilation avec **/CLR**, les variables globales et static sont par processus par défaut (n’avez pas besoin d’utiliser `__declspec(process)`.  
  
 Seules une variable globale, une variable membre static ou une variable locale static de type natif peuvent être marquées avec `__declspec(process)`.  
  
  
 `process` est valide uniquement lors de la compilation avec [/CLR](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Si vous souhaitez que chaque domaine d’application possède sa propre copie d’une variable globale, utilisez [appdomain](../cpp/appdomain.md).  
  
 Consultez [domaines d’Application et Visual C++](../dotnet/application-domains-and-visual-cpp.md) pour plus d’informations.  
  
## <a name="see-also"></a>Voir aussi  
 [__declspec](../cpp/declspec.md)   
 [Mots clés](../cpp/keywords-cpp.md)