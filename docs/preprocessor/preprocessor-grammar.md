---
title: "Syntaxe du préprocesseur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02b3597b035e3ea4bfa1670aa405109f4c01a077
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="preprocessor-grammar"></a>Syntaxe du préprocesseur
**#define**  *identifier* *token-string*opt  
  
 *#* **définir***identificateur*[**(** *identificateur*opt**,** *...*  **,** *identificateur*opt **)**] *chaîne de jeton*opt    
  
 **defined(**  *identifier* **)**  
  
 **defined**  *identifier*  
  
 `#include` **"***path-spec***"**  
  
 `#include` **\<***spécification de chemin d’accès***>**  
  
 **#line**  *digit-sequence*  **"** *filename* **"**opt  
  
 *#* **undef***identificateur*   
  
 **#error**  *token-string*  
  
 **#pragma**  *token-string*  
  
 *conditionnel* :  
 *If-partie elif-parties*opt*partie « else »*opt*endif en ligne*  
  
 *If-partie* :  
 *if-linetext*  
  
 *If-ligne* :  
 **#if**  *constant-expression*  
  
 **#ifdef**  *identifier*  
  
 **#ifndef**  *identifier*  
  
 *parties d’elif* :  
 *texte de la ligne d’elif*  
  
 *texte de ligne elif elif-parties*  
  
 *ligne elif* :  
 **#elif**  *constant-expression*  
  
 *partie « else »* :  
 *else-linetext*  
  
 *else-line* :  
 `#else`  
  
 *ligne endif* :  
 `#endif`  
  
 *digit-sequence* :  
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