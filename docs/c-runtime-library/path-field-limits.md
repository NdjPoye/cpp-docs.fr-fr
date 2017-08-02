---
title: Limites de champ de chemin | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
dev_langs:
- C++
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.openlocfilehash: e00104ada550d2510b031804d073098693144768
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="path-field-limits"></a>Limites de champ de chemin
## <a name="syntax"></a>Syntaxe  
  
```  
#include <stdlib.h>  
```  
  
## <a name="remarks"></a>Remarques  
 Ces constantes définissent la longueur maximale pour le chemin d’accès et pour les champs individuels dans le chemin d’accès.  
  
|Constante|Signification|  
|--------------|-------------|  
|`_MAX_DIR`|Longueur maximale du composant de répertoire|  
|`_MAX_DRIVE`|Longueur maximale du composant de lecteur|  
|`_MAX_EXT`|Longueur maximale du composant d’extension|  
|`_MAX_FNAME`|Longueur maximale du composant de nom de fichier|  
|`_MAX_PATH`|Longueur maximale du chemin d’accès complet|  
  
> [!NOTE]
>  Le Runtime C prend en charge les chemins d’accès jusqu'à 32768 caractères de longueur, mais il appartient au système d’exploitation, et en particulier au système de fichiers, de prendre en charge ces chemins d’accès plus longs. La somme des champs ne doit pas dépasser `_MAX_PATH` pour la compatibilité descendante intégrale avec les systèmes de fichiers FAT32. [!INCLUDE[win2kfamily](../c-runtime-library/includes/win2kfamily_md.md)], [!INCLUDE[WinXpFamily](../atl/reference/includes/winxpfamily_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] et le système de fichiers NTFS de Windows Vista prennent en charge les chemins d’accès jusqu'à 32768 caractères de longueur, mais uniquement lorsque vous utilisez les API Unicode. Lorsque vous utilisez des noms de chemin d’accès long, ajoutez les caractères \\\\?\ avant le chemin et utilisez les versions Unicode des fonctions du Runtime C.  
  
## <a name="see-also"></a>Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)
