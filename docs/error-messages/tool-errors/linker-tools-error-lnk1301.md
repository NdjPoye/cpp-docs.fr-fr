---
title: "Erreur LNK1301 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cfcdb90b967ce5f0e9eda8dded9b93db5bdcc268
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1301"></a>Erreur des outils Éditeur de liens LNK1301
Modules clr LTCG trouvés, incompatibles avec /LTCG : paramètre  
  
 Un module compilé avec /GL et /clr a été à l’éditeur de liens, ainsi qu’une des optimisations guidées par profil (PGO) paramètres passé de LTCG.  
  
 Optimisations guidées par profil ne sont pas pris en charge pour les modules / CLR.  
  
 Pour plus d'informations, voir :  
  
-   [/GL (Optimisation de l’ensemble du programme)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/LTCG (Génération de code durant l’édition de liens)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md)  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Ne pas compiler avec/CLR, ou ne pas lier avec l’un des paramètres PGO LTCG.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur LNK1301 :  
  
```  
// LNK1301.cpp  
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj  
// LNK1301 expected  
class MyClass {  
public:  
   int i;  
};  
```