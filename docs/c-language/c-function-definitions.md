---
title: "Définitions de fonction C | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function declarators
- function definitions
- declaring functions, about function declarations
- declaring functions, declarators
- functions [C], parameters
- declarators, functions
- function parameters, function definitions
- function body
- declaring functions, variables
ms.assetid: ebab23c8-6eb8-46f3-b21d-570cd8457a80
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a58adfefc5e2b3b5085a44c38dd392d3369421c8
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="c-function-definitions"></a>Définitions de fonction C
Une définition de fonction spécifie le nom de la fonction, les types et le nombre de paramètres qu’elle s’attend à recevoir et son type de retour. Une définition de fonction comprend également un corps de fonction avec les déclarations de ses variables locales, ainsi que les instructions qui déterminent ce que fait la fonction.  
  
## <a name="syntax"></a>Syntaxe  
 *translation-unit* :  
 *external-declaration*  
  
 *translation-unit external-declaration*  
  
 *external-declaration* : /\* Autorisé uniquement dans la portée (fichier) externe \*/  
 *function-definition*  
  
 `declaration`  
  
 *function-definition*: /\* Ici le déclarateur est le déclarateur de fonction \*/  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* est spécifique de Microsoft \*/  
  
 Les paramètres de prototype sont les suivants :  
  
 *declaration-specifiers* :  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *declaration-list* :  
 *déclaration*  
  
 *declaration-list declaration*  
  
 `declarator`:  
 *pointer* opt*direct-declarator*  
  
 *direct-declarator* : /\*Déclarateur de fonction \*/  
 *direct-declarator*  **(**  *parameter-type-list*  **)** /* Déclarateur de nouveau style \*/  
  
 *direct-declarator*  **(**  *identifier-list* opt**)** /* Déclarateur de style obsolète \*/  
  
 La liste des paramètres dans une définition utilise la syntaxe suivante :  
  
 *parameter-type-list* : /\* La liste de paramètrest \*/  
 *parameter-list*  
  
 *parameter-list* **, ...**  
  
 *parameter-list* :  
 *parameter-declaration*  
  
 *parameter-list* **,**  *parameter-declaration*  
  
 *parameter-declaration* :  
 *declaration-specifiers declarator*  
  
 *declaration-specifiers abstract declarator* opt  
  
 La liste des paramètres dans une définition de fonction de style ancien utilise la syntaxe suivante :  
  
 *identifier-list* : /\* Utilisé dans les définitions et les déclarations de fonction de style obsolète \*/  
 *identifier*  
  
 *identifier-list* **,**  *identifier*  
  
 La syntaxe du corps de la fonction est la suivante :  
  
 *compound-statement*: /\* Le corps de la fonction \*/  
 **{**  `declaration`-*list* opt*statement-list* opt**}**  
  
 Les seuls spécificateurs de classe de stockage pouvant modifier une déclaration de fonction sont `extern` et **static**. Le spécificateur `extern` signifie que la fonction peut être référencée à partir d'autres fichiers ; autrement dit, son nom est exporté vers l'éditeur de liens. Le spécificateur **static** signifie que la fonction ne peut pas être référencée à partir d'autres fichiers ; autrement dit, le nom n'est pas exporté par l'éditeur de liens. Si aucune classe de stockage n'apparaît dans une définition de fonction, `extern` est utilisé. Dans tous les cas, la fonction est toujours visible du point de définition jusqu'à la fin du fichier.  
  
 Les *declaration-specifiers* facultatifs et le `declarator` obligatoire spécifient ensemble le type de retour et le nom de la fonction. `declarator` est une combinaison de l'identificateur qui nomme la fonction et des parenthèses qui suivent le nom de fonction. L’élément non terminal *attribute-seq* facultatif est une fonctionnalité spécifique à Microsoft définie dans [Attributs de fonction](../c-language/function-attributes.md).  
  
 L'élément *direct-declarator* (dans la syntaxe `declarator`) spécifie le nom de la fonction définie et les identificateurs de ses paramètres. Si l'élément *direct-declarator* inclut *parameter-type-list*, la liste spécifie les types de tous les paramètres. Ce déclarateur sert également de prototype de fonction pour les appels ultérieurs à la fonction.  
  
 Un paramètre `declaration` présent dans *declaration-list* dans les définitions de fonction ne peut pas contenir de *storage-class-specifier* autre que **register**. Le *type-specifier* de la syntaxe *declaration-specifiers* peut être omis uniquement si la classe de stockage **register** est spécifiée pour une valeur de type `int`.  
  
 L'élément *compound-statement* est le corps de la fonction contenant des déclarations de variables locales, des références à des éléments déclarés extérieurement et des instructions.  
  
 Les sections [Attributs de fonction](../c-language/function-attributes.md), [Classe de stockage](../c-language/storage-class.md), [Type de retour](../c-language/return-type.md), [Paramètres](../c-language/parameters.md) et [Corps de la fonction](../c-language/function-body.md) décrivent les composants de la définition de fonction en détail.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../c-language/functions-c.md)