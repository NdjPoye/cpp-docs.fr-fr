---
title: '#<a name="ifdef-and-ifndef-directives-cc--microsoft-docs"></a>Directives ifdef et #ifndef (C/C++) | Documents Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '#ifndef'
- '#ifdef'
dev_langs: C++
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7a56212dc0943c79152b8485bea3a3082bfa73d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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