---
title: Classes de stockage C | Microsoft Docs
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
- static variables, lifetime
- storage classes
- lifetime, variables
- specifiers, storage class
- storage class specifiers, C storage classes
- storage duration
ms.assetid: 893fb929-f7a9-43dc-a0b3-29cb1ef845c1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2219ac079fecdb0f21215814885ee831d24f8f6e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="c-storage-classes"></a>Classes de stockage C
La « classe de stockage » d'une variable détermine si l'élément a une durée de vie « globale » ou « locale ». C appelle ces deux durées de vie « statique » et « auto ». Un élément avec une durée de vie globale existe et a une valeur tout au long de l'exécution du programme. Toutes les fonctions ont des durées de vie globales.  
  
 Un nouveau stockage est alloué aux variables automatiques ou à celles avec des durées de vie locales chaque fois que le contrôle d'exécution passe au bloc dans lequel elles sont définies. Lorsque l'exécution est retournée, les variables n'ont plus de valeurs significatives.  
  
 C fournit les spécificateurs de classe de stockage suivants :  
  
## <a name="syntax"></a>Syntaxe  
 *storage-class-specifier* :  
 **auto**  
  
 **register**  
  
 **static**  
  
 **extern**  
  
 **typedef**  
  
 **__declspec** ( *extended-decl-modifier-seq*) /* Spécifique de Microsoft \*/  
  
 Hormis pour `__declspec`, vous ne pouvez utiliser qu'un seul *storage-class-specifier* dans *declaration-specifier* dans une déclaration. Si aucune spécification classe-stockage n'est donnée, les déclarations dans un bloc créent des objets automatiques.  
  
 Les éléments déclarés avec le spécificateur **auto** ou **register** ont des durées de vie locales. Les éléments déclarés avec le spécificateur **static** ou `extern` ont des durées de vie globales.  
  
 Puisque `typedef` et `__declspec` sont sémantiquement différents des quatre autres éléments terminaux *storage-class-specifier*, ils sont traités séparément. Pour des informations spécifiques sur `typedef`, consultez [Déclarations typedef](../c-language/typedef-declarations.md). Pour des informations spécifiques sur `__declspec`, consultez [Attributs étendus de classe de stockage](../c-language/c-extended-storage-class-attributes.md).  
  
 Le positionnement des déclarations de variables et des fonctions dans des fichiers sources affecte également la classe de stockage et la visibilité. Les déclarations en dehors de toutes les définitions de fonction sont supposées apparaître « au niveau externe ». Les déclarations dans des définitions de fonction apparaissent au « niveau interne ».  
  
 La signification exacte de chaque spécificateur de classe de stockage dépend de deux facteurs :  
  
-   Si la déclaration apparaît au niveau externe ou interne  
  
-   Si l'élément déclaré est une variable ou une fonction  
  
 [Les spécificateurs de classe de stockage des déclarations au niveau externe](../c-language/storage-class-specifiers-for-external-level-declarations.md) et [Spécificateurs de classe de stockage des déclarations au niveau interne](../c-language/storage-class-specifiers-for-internal-level-declarations.md) décrivent les éléments terminaux *storage-class-specifier* dans chaque type de déclaration et expliquent le comportement par défaut lorsque le *storage-class-specifier* est omis dans une variable. La rubrique [Spécificateurs de classe de stockage avec des déclarations de fonction](../c-language/storage-class-specifiers-with-function-declarations.md) décrit les spécificateurs de classe de stockage utilisés avec les fonctions.  
  
## <a name="see-also"></a>Voir aussi  
 [Déclarations et types](../c-language/declarations-and-types.md)