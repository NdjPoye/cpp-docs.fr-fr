---
title: Erreur du compilateur C3171 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3171
dev_langs: C++
helpviewer_keywords: C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed053e37dfbf5f3c85cf1f8ec44912eca3148315
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3171"></a>Erreur du compilateur C3171
'module' : Impossible de spécifier des attributs de module différents dans un projet  
  
 [module](../../windows/module-cpp.md) attributs avec les listes de paramètres différentes ont été trouvés dans deux des fichiers d’une compilation. Un seul `module` attribut peut être spécifié par compilation.  
  
 Identiques `module` attributs peuvent être spécifiés dans plusieurs fichiers de code source.  
  
 Par exemple, si les éléments suivants `module` attributs ont été trouvés :  
  
```  
// C3171.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];  
int main() {}  
```  
  
 Puis,  
  
```  
// C3171b.cpp  
// compile with: C3171.cpp  
// C3171 expected  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];  
```  
  
 le compilateur génère l’erreur C3171 (Notez les valeurs de version différente).