---
title: Flux d&quot;octets et flux larges | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Byte and Wide Streams
dev_langs:
- C++
helpviewer_keywords:
- byte streams
- wide streams
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
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
ms.openlocfilehash: c916caf1ee0b39567813921401ee02cbda83d222
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="byte-and-wide-streams"></a>Flux d'octets et flux larges
Un flux d'octets traite un fichier comme une séquence d'octets. Dans le programme, le flux est la même séquence d’octets.  
  
 En revanche, un flux large traite un fichier comme une séquence de caractères multioctets généralisés, qui peut avoir un large éventail de règles de codage. (Les fichiers texte et binaires sont toujours lus et écrits comme décrit précédemment.) Dans le programme, le flux ressemble à la séquence correspondante de caractères larges. Des conversions entre les deux représentations se produisent dans la bibliothèque C standard. Les règles de conversion peuvent, en principe, être modifiées par un appel à [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) qui modifie la catégorie `LC_CTYPE`. Chaque flux large détermine ses règles de conversion au moment où il devient orienté large et les conserve même si la catégorie `LC_CTYPE` change ultérieurement.  
  
 Le positionnement dans un flux large subit les mêmes limitations que pour les flux de texte. En outre, l’indicateur de position de fichier peut également avoir à traiter avec un encodage dépendant de l’état. En règle générale, il inclut à la fois un décalage d’octets dans le flux de données et un objet de type `mbstate_t`. Par conséquent, la seule méthode fiable pour obtenir une position de fichier dans un flux large est d’appeler [fgetpos](../c-runtime-library/reference/fgetpos.md), et la seule méthode fiable pour restaurer un emplacement obtenu de cette façon est d’appeler [fsetpos](../c-runtime-library/reference/fsetpos.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers et flux](../c-runtime-library/files-and-streams.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
