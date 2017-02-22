---
title: "Erreur des outils &#201;diteur de liens LNK1301 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1301"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1301"
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur des outils &#201;diteur de liens LNK1301
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

modules clr LTCG trouvés, incompatibles avec \/LTCG :paramètre  
  
 Un module compilé avec \/clr et \/GL a été passé à l'éditeur de liens avec l'un des paramètres d'optimisations guidées par profil \(PGO\) de \/LTCG.  
  
 Les optimisations guidées par profil ne sont pas prises en charge pour les modules \/clr.  
  
 Pour plus d'informations, consultez :  
  
-   [\/GL \(Optimisation de l'ensemble du programme\)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [\/LTCG \(Génération de code durant l'édition de liens\)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md)  
  
### Pour corriger cette erreur  
  
1.  Ne compilez pas avec \/clr ou n'effectuez pas de liaison avec l'un des paramètres PGO à \/LTCG.  
  
## Exemple  
 L'exemple suivant génère l'erreur LNK1301 :  
  
```  
// LNK1301.cpp  
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj  
// LNK1301 expected  
class MyClass {  
public:  
   int i;  
};  
```