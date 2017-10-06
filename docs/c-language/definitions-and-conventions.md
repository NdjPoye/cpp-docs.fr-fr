---
title: "Définitions et Conventions | Microsoft Docs"
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
- nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: fa335f2eec22e6f3008abe49f7ac36308ce0ad9a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="definitions-and-conventions"></a>Définitions et conventions
Les terminaux sont des points de terminaison dans une définition de syntaxe. Aucune autre résolution n'est possible. Les terminaux incluent l'ensemble des mots réservés et des identificateurs définis par l'utilisateur.  
  
 Les non terminaux sont des espaces réservés dans la syntaxe qui sont définis ailleurs dans ce résumé de syntaxe. Les définitions peuvent être récursives.  
  
 Un composant facultatif est indiqué par l'élément opt indicé. Par exemple :  
  
```  
  
{  
expression <SUB>opt</SUB> }  
```  
  
 indique une expression facultative entre accolades.  
  
 Les conventions syntaxiques utilisent différents attributs de police pour différents composants de la syntaxe. Les symboles et les polices sont comme suit :  
  
|Attribut|Description|  
|---------------|-----------------|  
|*nonterminal*|Le type italique indique des symboles non terminaux.|  
|**const**|Les symboles terminaux en gras sont des mots réservés littéraux et des symboles littéraux qui doivent être écrits comme indiqué. Les caractères situés dans ce contexte respectent toujours la casse.|  
|option|Les symboles non terminaux suivis de l'indication « option » sont toujours facultatifs.|  
|police par défaut|Les caractères dans le jeu décrit ou répertorié dans cette police peuvent être utilisés comme terminaux dans les instructions C.|  
  
 Un signe deux-points (**:**) qui suit un symbole non terminal introduit sa définition. Les définitions alternatives figurent sur des lignes distinctes, sauf lorsqu'elles sont précédées des mots « one of ».  
  
## <a name="see-also"></a>Voir aussi  
 [Résumé de syntaxe du langage C](../c-language/c-language-syntax-summary.md)
