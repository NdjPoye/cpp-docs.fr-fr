---
title: "Intégration des noms de fichiers entre crochets | Microsoft Docs"
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
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: f118417a7ed2fdf8cad77775e144b81655c56916
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="including-bracketed-filenames"></a>Intégration des noms de fichiers entre crochets
**ANSI 3.8.2** Méthode utilisée pour localiser les fichiers à inclure  
  
 Pour les caractéristiques du fichier placées entre crochets pointus, le préprocesseur n'effectue pas de recherche dans les répertoires des fichiers parents. Le fichier « parent » est le fichier qui contient la directive [#include](../preprocessor/hash-include-directive-c-cpp.md). Au lieu de cela, il commence par rechercher le fichier dans les répertoires spécifiés sur la ligne de commande du compilateur située après /I. Si l'option /I est absente ou échoue, le préprocesseur utilise la variable d'environnement INCLUDE pour rechercher tous les fichiers Include entre crochets pointus. La variable d’environnement INCLUDE peut contenir plusieurs chemins séparés par des points-virgules (**;**). Si plusieurs répertoires figurent dans l'option /I ou la variable d'environnement INCLUDE, le préprocesseur les traite dans l'ordre dans lequel ils apparaissent.  
  
## <a name="see-also"></a>Voir aussi  
 [Directives de prétraitement](../c-language/preprocessing-directives.md)
