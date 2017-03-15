---
title: "check_stack | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.check_stack"
  - "check_stack_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "check_stack (pragma)"
  - "pragmas, check_stack"
  - "pragmas, tableau d'utilisation de check_stack"
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# check_stack
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fait en sorte que le compilateur désactive les tests de pile si **off** \(ou **–**\) est spécifié, ou qu'il active les tests de pile si **on** \(ou **\+**\) est spécifié.  
  
## Syntaxe  
  
```  
  
      #pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | –}  
```  
  
## Notes  
 Si aucun argument n'est fourni, les tests de pile sont traités en fonction de la valeur par défaut.  Ce pragma est appliqué à la première fonction définie après détection du pragma.  Les tests de pile ne font partie ni des macros, ni des fonctions générées inline.  
  
 Si vous ne fournissez pas d'argument pour le pragma **check\_stack**, le comportement du contrôle de pile redevient celui spécifié sur la ligne de commande.  Pour plus d'informations, consultez [Référence du compilateur](../build/reference/compiler-options.md).  L'interaction entre **\#pragma check\_stack** et l'option [\/Gs](../build/reference/gs-control-stack-checking-calls.md) est résumée dans le tableau suivant.  
  
### Utilisation du pragma check\_stack  
  
|Syntaxe|Compilé avec<br /><br /> Option \/Gs ?|Action|  
|-------------|------------------------------------|------------|  
|**\#pragma check\_stack\( \)** ou<br /><br /> **\#pragma check\_stack**|Oui|Désactive la vérification de la pile pour les fonctions qui suivent|  
|**\#pragma check\_stack\( \)** ou<br /><br /> **\#pragma check\_stack**|Non|Active la vérification de la pile pour les fonctions qui suivent|  
|**\#pragma check\_stack\(on\)**<br /><br /> ou **\#pragma check\_stack \+**|Oui ou non|Active la vérification de la pile pour les fonctions qui suivent|  
|**\#pragma check\_stack\(off\)**<br /><br /> ou **\#pragma check\_stack –**|Oui ou non|Désactive la vérification de la pile pour les fonctions qui suivent|  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)