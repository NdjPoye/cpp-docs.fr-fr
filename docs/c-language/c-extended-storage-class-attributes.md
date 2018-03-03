---
title: "Attributs étendus de classe de stockage C | Microsoft Docs"
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
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 972a8dc27283839ce1eade0e1e9b81dc92998b15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="c-extended-storage-class-attributes"></a>Attributs étendus de classe de stockage C
**Section spécifique à Microsoft**  
  
 Des informations plus récentes à ce sujet sont disponibles dans [__declspec (Référence C++)](../cpp/declspec.md).  
  
 La syntaxe à attributs étendus simplifie et normalise les extensions spécifiques à Microsoft pour le langage C. Les attributs de classe de stockage qui utilisent la syntaxe à attributs étendus incluent thread, naked, dllimport et dllexport.  
  
 La syntaxe à attributs étendus utilisée pour la spécification des informations de classe de stockage utilise le mot clé __declspec, qui indique qu'une instance d'un type donné doit être stockée avec un attribut de classe de stockage spécifique à Microsoft (thread, naked, dllimport ou dllexport). Parmi les exemples d'autres modificateurs de classe de stockage figurent les mots clés static et extern. Toutefois, ces mots clés font partie de la norme ANSI C et, en tant que tels, ne sont pas couverts par la syntaxe à attributs étendus.  
  
## <a name="syntax"></a>Syntaxe  
 *storage-class-specifier* :  
 `__declspec` ( *extended-decl-modifier-seq* ) /* Spécifique de Microsoft \*/  
  
 *extended-decl-modifier-seq* :  
 *extended-decl-modifier* opt  
  
 *extended-decl-modifier-seq extended-decl-modifier*  
  
 *extended-decl-modifier* :  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
 Un espace blanc sépare les modificateurs de déclaration. Notez que *extended-decl-modifier-seq* peut être vide, auquel cas __declspec n'a aucun effet.  
  
 Les attributs de classe de stockage thread, naked, dllimport et dllexport sont une propriété uniquement de la déclaration des données ou de la fonction à laquelle ils sont appliqués. Ils ne redéfinissent pas les attributs de type de la fonction elle-même. L'attribut thread affecte uniquement les données. L'attribut naked affecte uniquement les fonctions. Les attributs dllimport et dllexport affectent les fonctions et les données.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Déclarations et types](../c-language/declarations-and-types.md)