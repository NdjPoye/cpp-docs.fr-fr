---
title: processus | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c50948d613a40a03d0249e1930943ef61c855b9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
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