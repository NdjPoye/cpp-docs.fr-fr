---
title: "Spécificateurs de type C | Microsoft Docs"
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
- type specifiers, C
- specifiers, type
ms.assetid: fbe13441-04c3-4829-b047-06d374adc2b6
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e797f8216b67e2eb182218be8fa0857cf9b29fa0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="c-type-specifiers"></a>Spécificateurs de type C
Les spécificateurs de type dans les déclarations définissent le type d'une variable ou d'une déclaration de fonction.  
  
## <a name="syntax"></a>Syntaxe  
 *type-specifier* :  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **unsigned**  
  
 *struct-or-union-specifier*  
  
 *enum-specifier*  
  
 *typedef-name*  
  
 Les types signed **char**, **signed int**, **signed short int** et **signed long int**, ainsi que leurs équivalents `unsigned` et `enum`, sont appelés types « intégraux ». Les spécificateurs de type **float**, **double** et `long double` sont appelés types « flottants » ou « à virgule flottante ». Vous pouvez utiliser n'importe quel spécificateur de type intégral ou à virgule flottante dans une variable ou une déclaration de fonction. Si aucun *type-specifier* n'est fourni dans une déclaration, `int` est utilisé par défaut.  
  
 Les mots clés facultatifs **signed** et `unsigned` peuvent précéder ou suivre tout type intégral, à l'exception d' `enum`, et peuvent également être utilisés seuls comme spécificateurs de type, auquel cas ils sont compris respectivement comme **signed int** et `unsigned int`. S'il est utilisé seul, le mot clé `int` est supposé être **signed**. S'ils sont utilisés seuls, les mots clés **long** et **short** sont compris comme **long int** et `short int`.  
  
 Les types énumération sont considérés comme des types de base. Les spécificateurs de type pour les types énumération sont traités dans [Déclarations d'énumération](../c-language/c-enumeration-declarations.md).  
  
 Le mot clé `void` a trois utilisations : spécifier un type de retour de fonction, spécifier une liste de types d'arguments pour une fonction qui n'accepte pas d'argument et spécifier un pointeur vers un type non spécifié. Vous pouvez utiliser le type `void` pour déclarer des fonctions qui ne retournent aucune valeur ou pour déclarer un pointeur vers un type non spécifié. Pour plus d’informations sur `void` lorsqu’il apparaît seul entre les parenthèses qui suivent un nom de fonction, consultez [Arguments](../c-language/arguments.md).  
  
 **Section spécifique à Microsoft**  
  
 La vérification de type est maintenant conforme à la spécification ANSI, ce qui signifie que le type **short** et le type `int` sont des types distincts. Par exemple, voici une redéfinition dans le compilateur C Microsoft qui était acceptée par les versions précédentes du compilateur.  
  
```  
int   myfunc();  
short myfunc();  
```  
  
 Cet exemple suivant génère également un avertissement concernant l'indirection vers différents types :  
  
```  
int *pi;  
short *ps;  
  
ps = pi;  /* Now generates warning */  
```  
  
 Le compilateur C Microsoft génère également des avertissements pour les différences de signe. Exemple :  
  
```  
signed int *pi;  
unsigned int *pu  
  
pi = pu;  /* Now generates warning */  
```  
  
 Les expressions `void` de type sont évaluées quant à leurs effets secondaires. Vous ne pouvez en aucune manière utiliser la valeur (inexistante) d'une expression de type `void`, ni convertir une expression `void` (par conversion implicite ou explicite) en un type autre que `void`. Si vous utilisez une expression d'un autre type dans un contexte où une expression `void` est requise, sa valeur est ignorée.  
  
 Pour être conforme à la spécification ANSI, **void\*\*** ne peut pas être utilisé comme **int\*\***. Seul **void\*** peut être utilisé comme pointeur vers un type non spécifié.  
  
 **FIN de la section spécifique à Microsoft**  
  
 Vous pouvez créer des spécificateurs de type supplémentaires avec des déclarations `typedef`, comme décrit dans [Déclarations typedef](../c-language/typedef-declarations.md). Pour plus d'informations sur la taille de chaque type, consultez [Stockage des types de base](../c-language/storage-of-basic-types.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Déclarations et types](../c-language/declarations-and-types.md)