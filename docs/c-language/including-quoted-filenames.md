---
title: Inclusion des noms de fichier entre guillemets | Microsoft Docs
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
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 70b5e68fc8a3c0c23b291220e4faf387e9aa11c2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="including-quoted-filenames"></a>Intégration des noms de fichiers entre guillemets
**ANSI 3.8.2** Prise en charge des noms entre guillemets pour les fichiers à inclure  
  
 Si vous spécifiez un chemin d’accès complet et non équivoque pour le fichier Include entre guillemets doubles (" "), le préprocesseur recherche uniquement dans le répertoire défini par ce chemin d’accès et ignore les répertoires standard.  
  
 Pour les fichiers Include spécifiés comme « spécification de chemin d’accès » [#include](../preprocessor/hash-include-directive-c-cpp.md), la recherche dans les répertoires commence par les répertoires du fichier parent, puis se poursuit par les répertoires de tous les fichiers grand-parents. Ainsi, la recherche commence par rapport au répertoire contenant le fichier source actuellement traitée. S'il n'existe aucun fichier grand-parent et que le fichier n'a pas été trouvé, la recherche se poursuit comme si le nom de fichier était placé entre crochets pointus.  
  
## <a name="see-also"></a>Voir aussi  
 [Directives de prétraitement](../c-language/preprocessing-directives.md)