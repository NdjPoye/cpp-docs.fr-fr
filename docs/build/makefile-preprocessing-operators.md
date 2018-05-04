---
title: Opérateurs de prétraitement d’un makefile | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], makefile preprocessing
- EXIST operator
- preprocessing NMAKE makefile operators
- NMAKE program, operators
- DEFINED operator
- makefiles, preprocessing operators
ms.assetid: a46e4d39-afdb-43c1-ac3b-025d33e6ebdb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9a99bf6388a4aa15b2126aca8e09210b7202d46
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="makefile-preprocessing-operators"></a>Opérateurs de prétraitement d'un makefile
Les expressions de prétraitement makefile peuvent utiliser des opérateurs qui agissent sur des valeurs constantes, les codes de sortie des commandes, chaînes, macros et chemins d’accès du système de fichiers. Pour évaluer l'expression, le préprocesseur commence par développer les macros, puis il exécute les commandes et il effectue enfin les opérations. Les opérations sont évaluées dans l'ordre de leur groupement explicite entre parenthèses, puis dans l'ordre de priorité des opérateurs. Il en résulte une valeur constante.  
  
 L'opérateur `DEFINED` est un opérateur logique qui agit sur un nom de macro. L’expression `DEFINED(` *nom_macro* `)` a la valeur true si *nom_macro* est défini, même si elle n’a pas de valeur assignée. `DEFINED` associé à `!IF` ou `!ELSE IF` équivaut à `!IFDEF` ou `!ELSE IFDEF`. Toutefois, à la différence de ces directives, `DEFINED` peut être utilisé dans des expressions complexes.  
  
 L'opérateur `EXIST` est un opérateur logique qui agit sur un chemin d'accès du système de fichiers. `EXIST(`*chemin d’accès* `)` a la valeur true si *chemin d’accès* existe. Le résultat d'`EXIST` peut être utilisé dans des expressions binaires. Si *chemin d’accès* contient des espaces, placez-le entre guillemets doubles.  
  
 Pour comparer deux chaînes, utilisez l'opérateur d'égalité (`==`) ou l'opérateur d'inégalité (`!=`). Placez les chaînes entre guillemets doubles.  
  
 Les constantes entières peuvent utiliser les opérateurs unaires pour la négation numérique (`-`), le complément à un (`~`) et la négation logique (`!`).  
  
 Les expressions peuvent utiliser les opérateurs suivants. Les opérateurs de même priorité sont regroupés ensemble et les groupes sont répertoriés dans l'ordre de priorité décroissante. Les opérateurs unaires s'associent avec l'opérande de droite. Les opérateurs binaires de même priorité associent les opérandes de gauche à droite.  
  
|Opérateur|Description|  
|--------------|-----------------|  
|`DEFINED(` *nom_macro* `)`|Génère une valeur logique pour l’état actuel de la définition de *nom_macro*.|  
|`EXIST(` *chemin d’accès* `)`|Génère une valeur logique pour l’existence d’un fichier au *chemin d’accès*.|  
|||  
|`!`|NOT logique unaire.|  
|`~`|Complément à un unaire|  
|`-`|Négation unaire|  
|||  
|`*`|Multiplication|  
|`/`|Division|  
|`%`|Modulo (reste)|  
|||  
|`+`|Addition|  
|`-`|Soustraction|  
|||  
|`<<`|Déplacement à gauche au niveau du bit|  
|`>>`|Déplacement à droite au niveau du bit|  
|||  
|`<=`|Inférieur ou égal à|  
|`>=`|Supérieur ou égal à|  
|`<`|Inférieur à|  
|`>`|Supérieur à|  
|||  
|`==`|Égalité|  
|`!=`|Inégalité|  
|||  
|`&`|AND au niveau du bit|  
|`^`|XOR au niveau du bit|  
|`&#124;`|OR au niveau du bit|  
|||  
|`&&`|AND logique|  
|||  
|`&#124;&#124;`|OR logique|  
  
> [!NOTE]
>  L'opérateur XOR au niveau du bit (`^`) est le même que le caractère d'échappement, et il doit former une séquence d'échappement (sous la forme `^^`) quand il est utilisé dans une expression.  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions utilisées dans le prétraitement d’un makefile](../build/expressions-in-makefile-preprocessing.md)