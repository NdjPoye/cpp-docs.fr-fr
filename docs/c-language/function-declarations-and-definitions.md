---
title: "Définitions et déclarations de fonctions | Microsoft Docs"
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
- local declarations
- function definitions, function declarations
- declaring functions, function definitions
- internal declarations
- external declarations
- function prototypes, basics
- external linkage, function declarations
- declaring functions
ms.assetid: 43fd98eb-7441-4473-a5d9-fc88c75577f7
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: ea315c065e6f76215939bc4ccd70bcc907361ff4
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="function-declarations-and-definitions"></a>Définitions et déclarations de fonctions
Les prototypes de fonction établissent le nom de la fonction, son type de retour et le type et le nombre de ses paramètres formels. Une définition de fonction comprend le corps de la fonction.  
  
## <a name="remarks"></a>Notes  
 Les déclarations de fonctions et de variables peuvent apparaître à l'intérieur ou à l'extérieur d'une définition de fonction. Toute déclaration présente dans une définition de fonction est dite apparaître au niveau interne ou local. Une déclaration extérieure à toutes les définitions de fonction est dite apparaître au niveau externe, global ou de la portée du fichier. Les définitions variables, comme les déclarations, peuvent apparaître au niveau interne (dans une définition de fonction) ou au niveau externe (à l'extérieur de toutes les définitions de fonction). Les définitions de fonction ont toujours lieu au niveau externe. Les définitions de fonction sont décrites plus loin dans [Définitions de fonction](../c-language/c-function-definitions.md). Les prototypes de fonction sont décrites dans [Prototypes de fonction](../c-language/function-prototypes.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers sources et programmes sources](../c-language/source-files-and-source-programs.md)
