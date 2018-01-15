---
title: "Syntaxe du préprocesseur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 797d4bf4274a92ca4f265d01579698c0f9c6a4a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="preprocessor-grammar"></a>Syntaxe du préprocesseur
**#define***identificateur* *chaîne de jeton*opt    
  
 *#***définir***identificateur*[**(** *identificateur*opt**,** *...*  **,** *identificateur*opt **)**] *chaîne de jeton*opt    
  
 **défini (***identificateur* **)**   
  
 **défini***identificateur*   
  
 `#include`**»***spécification de chemin d’accès***»**  
  
 `#include` **\<**  *spécification de chemin d’accès***>**  
  
 **#line***séquence de chiffres***»** *nom de fichier* **»**opt      
  
 *#***undef***identificateur*   
  
 **#error***chaîne de jeton*   
  
 **#pragma***chaîne de jeton*   
  
 *conditionnel* :  
 *If-partie elif-parties*opt*partie « else »*opt*endif en ligne*  
  
 *If-partie* :  
 *If-linetext*  
  
 *If-ligne* :  
 **#if***expression constante*   
  
 **#ifdef***identificateur*   
  
 **#ifndef***identificateur*   
  
 *parties d’elif* :  
 *texte de la ligne d’elif*  
  
 *texte de ligne elif elif-parties*  
  
 *ligne elif* :  
 **#elif***expression constante*   
  
 *partie « else »* :  
 *Else-linetext*  
  
 *ligne Else* :  
 `#else`  
  
 *ligne endif* :  
 `#endif`  
  
 *séquence de chiffres* :  
 *digit*  
  
 *digit-sequence digit*  
  
 *chiffre* : un des  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *chaîne de jeton* :  
 Chaîne de jetons  
  
 *jeton* :  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *nom de fichier* :  
 Nom de fichier du système d'exploitation conforme  
  
 *spécification de chemin d’accès* :  
 Chemin d’accès de fichier conforme  
  
 *texte* :  
 Toute séquence de texte  
  
> [!NOTE]
>  Les éléments non terminaux suivants sont développés dans les [Conventions lexicales](../cpp/lexical-conventions.md) section de la *référence du langage C++*: `constant`, `constant` - *expression* , *identificateur*, *mot clé*, `operator`, et `punctuator`.  
  
## <a name="see-also"></a>Voir aussi  
 [Résumé de la grammaire (C/C++)](../preprocessor/grammar-summary-c-cpp.md)