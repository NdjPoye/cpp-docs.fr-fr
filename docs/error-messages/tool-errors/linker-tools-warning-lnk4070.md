---
title: "LNK4070 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4070
dev_langs: C++
helpviewer_keywords: LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c3c683593b9019851b1a330a613adcf7a18c4a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4070"></a>Avertissement des outils Éditeur de liens LNK4070
Directive/out : NomFichier dans. EXP est différente de nom de fichier de sortie 'NomFichier' ; directive ignorée  
  
 Le `filename` spécifié dans le [nom](../../build/reference/name-c-cpp.md) ou [bibliothèque](../../build/reference/library.md) instruction lors de la création du fichier .exp est différente de la sortie `filename` qui a été supposé par défaut ou spécifiée avec la [/OUT](../../build/reference/out-output-file-name.md) option.  
  
 Vous verrez cet avertissement si vous modifiez le nom d’un fichier de sortie dans l’environnement de développement et où le fichier du projet .def n’a pas mis à jour. Mettre à jour manuellement le fichier .def pour résoudre cet avertissement.  
  
 Un programme client qui utilise la DLL résultante peut rencontrer des problèmes.