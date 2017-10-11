---
title: "Portée et visibilité | Microsoft Docs"
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
- scope, levels
- visibility
- file scope [C++]
ms.assetid: a019eb7c-66ed-46a7-bc9f-89a963930a56
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 9e9dca1b95af3971045a1ce86807ef28be096546
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="scope-and-visibility"></a>Portée et visibilité
La « visibilité » d'un identificateur détermine les parties du programme où un identificateur peut être référencé (sa « portée »). Un identificateur est visible (c- à-d. qu'il peut être utilisé) uniquement dans les parties d'un programme entourées par sa « portée », qui peuvent être limitées (afin d'augmenter les restrictions) au fichier, à la fonction, au bloc ou au prototype de fonction dans lequel il apparaît. La portée d'un identificateur est la partie du programme où il peut être utilisé. Cela est parfois appelé « portée lexicale ». Il existe quatre types de portée : fonction, fichier, bloc, et prototype de fonction.  
  
 Tous les identificateurs exceptées les étiquettes ont leur portée déterminée par le niveau auquel la déclaration se produit. Les règles suivantes pour chaque type de portée régissent la visibilité des identificateurs à l'intérieur d'un programme :  
  
 Portée du fichier  
 Le spécificateur de déclarateur ou de type pour un identificateur à la portée du fichier apparaît en dehors de tout bloc ou liste de paramètres et est accessible à partir de tout emplacement dans l'unité de traduction après sa déclaration. Les noms d'identificateurs dans la portée du fichier sont souvent appelés « globaux » ou « externes. » La portée d'un identificateur global commence au point de sa définition ou déclaration et se termine à la fin de l'unité de traduction.  
  
 Portée de la fonction  
 Une étiquette est le seul type d'identificateur qui a une portée de fonction. Une étiquette est déclarée implicitement par son utilisation dans une instruction. Les noms d'étiquettes doivent être uniques dans une fonction. (Pour plus d'informations sur les étiquettes et les noms d'étiquettes, consultez [Instructions goto et étiquetées](../c-language/goto-and-labeled-statements-c.md).)  
  
 Portée de bloc  
 Le spécificateur de déclarateur ou de type pour un identificateur avec portée de bloc apparaît à l'intérieur d'un bloc ou dans la liste des déclarations de paramètre formel dans une définition de fonction. Il est visible uniquement à partir du point de sa déclaration ou définition à la fin du bloc qui contient sa déclaration ou définition. Sa portée est limitée à ce bloc et à tous les blocs imbriqués dans ce bloc et se termine à l'accolade qui ferme le bloc associé. Ces identificateurs sont parfois appelés « variables locales ».  
  
 Portée de prototype de fonction  
 Le spécificateur de déclarateur ou de type pour un identificateur avec portée de prototype de fonction apparaît dans la liste des déclarations de paramètre dans un prototype de fonction (pas dans une déclaration de fonction). Sa portée se termine à la fin du déclarateur de fonction.  
  
 Les déclarations appropriées pour rendre des variables visibles dans d'autres fichiers sources sont décrites dans [Classes de stockage](../c-language/c-storage-classes.md). Toutefois, les variables et les fonctions déclarées au niveau externe avec le spécificateur de classe de stockage **statique** sont visibles uniquement dans le fichier source dans lequel elles sont définies. Toutes les autres fonctions sont visibles globalement.  
  
## <a name="see-also"></a>Voir aussi  
 [Durée de vie, portée, visibilité et liaison](../c-language/lifetime-scope-visibility-and-linkage.md)
