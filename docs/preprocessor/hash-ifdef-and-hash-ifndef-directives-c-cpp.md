---
title: '#Directives ifdef et #ifndef (C/C++) | Documents Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#ifndef'
- '#ifdef'
dev_langs:
- C++
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8f1a10e9d8437b71591efc9ce2915c9f485e0c4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ifdef-and-ifndef-directives-cc"></a>Directives #ifdef et #ifndef (C/C++)
Le **#ifdef** et **#ifndef** directives effectuent la même tâche que la `#if` directive lorsqu’il est utilisé avec **défini**( *identificateur* ).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## <a name="remarks"></a>Notes  
 Vous pouvez utiliser la **#ifdef** et **#ifndef** directives n’importe où `#if` peut être utilisé. Le **#ifdef** *identificateur* instruction équivaut à `#if 1` lorsque *identificateur* a été défini, et elle est équivalente à `#if 0` lorsque *identificateur* n’a pas été défini ou a été supprimée avec le `#undef` la directive. Ces directives vérifient uniquement la présence ou l'absence d'identificateurs définis avec `#define`, et non d'identificateurs déclarés dans le code source C ou C++.  
  
 Ces directives sont fournies uniquement pour des raisons de compatibilité avec les versions antérieures du langage. Le **défini (** *identificateur* **)** expression constante utilisée avec la `#if` directive est préférée.  
  
 Le **#ifndef** directive vérifie l’inverse de la condition vérifiée par **#ifdef**. Si l'identificateur n'a pas été défini (ou si sa définition a été supprimée avec `#undef`), la condition est vraie (non nulle). Sinon, la condition n'est pas vérifiée (0).  
  
 **Section spécifique à Microsoft**  
  
 Le *identificateur* peuvent être passés à partir de la ligne de commande à l’aide de l’option /D. Jusqu'à 30 macros peuvent être spécifiées avec /D.  
  
 Cela est utile pour vérifier si une définition existe, car une définition peut être transmise à partir de la ligne de commande. Exemple :  
  
```  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)