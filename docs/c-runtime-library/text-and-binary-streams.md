---
title: Flux texte et binaires | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- binary streams
- text streams
ms.assetid: 57035e4a-955d-4e04-a560-fcf67ce68b4e
caps.latest.revision: 6
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
ms.openlocfilehash: b3f0a7603c2d3732c693c509e310a5a00a99300f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="text-and-binary-streams"></a>Flux texte et binaires
Un flux de texte se compose d'une ou de plusieurs lignes de texte qui peuvent être écrites sur un affichage orienté texte afin qu'elles puissent être lues. Lors de la lecture d'un flux de texte, le programme lit `NL` (saut de ligne) à la fin de chaque ligne. Lors de l'écriture dans un flux de texte, le programme écrit `NL` pour signaler la fin d'une ligne. Pour faire correspondre différentes conventions dans les environnements cibles pour représenter le texte contenu dans les fichiers, les fonctions de la bibliothèque peuvent modifier le nombre et les représentations des caractères transmis entre le programme et un flux de texte.  
  
 Par conséquent, le positionnement dans un flux de texte est limité. Vous pouvez obtenir l'indicateur de position de fichier actuel en appelant [fgetpos](../c-runtime-library/reference/fgetpos.md) ou [ftell](../c-runtime-library/reference/ftell-ftelli64.md). Vous pouvez positionner un flux de texte à un emplacement obtenu de cette façon, ou au début ou à la fin du flux, en appelant [fsetpos](../c-runtime-library/reference/fsetpos.md) ou [fseek](../c-runtime-library/reference/fseek-fseeki64.md). Tout autre changement de position risque de ne pas être pris en charge.  
  
 Pour une portabilité maximale, le programme ne doit pas écrire :  
  
-   Fichiers vides.  
  
-   Espaces à la fin d'une ligne.  
  
-   Lignes partielles (en omettant `NL` à la fin d'un fichier).  
  
-   Caractères autres que les caractères imprimables, NL et `HT` (tabulation horizontale).  
  
 Si vous suivez ces règles, la séquence de caractères que vous lisez à partir d'un flux de texte (en tant que caractères octets ou multioctets) correspond à la séquence de caractères que vous avez écrits dans le flux de texte lors de la création du fichier. Sinon, les fonctions de la bibliothèque peuvent supprimer un fichier créé s'il est vide lorsque vous le fermez. Elles peuvent également modifier ou supprimer les caractères que vous écrivez dans le fichier.  
  
 Un flux binaire se compose d'un ou de plusieurs octets d'informations aléatoires. Vous pouvez écrire la valeur stockée dans un objet aléatoire dans un flux binaire (orienté octet) et lire exactement le contenu stocké dans l'objet lors de son écriture. Les fonctions de la bibliothèque ne modifient pas les octets transmis entre l'application et un flux binaire. Elles peuvent, toutefois, ajouter un nombre aléatoire d'octets null au fichier que vous écrivez avec un flux binaire. Le programme doit traiter ces octets null supplémentaires à la fin d'un flux binaire.  
  
 Par conséquent, le positionnement dans un flux binaire est bien défini, à l'exception du positionnement relatif à la fin du flux. Vous pouvez obtenir et modifier l'indicateur de position de fichier actuel de la même manière que pour un flux de texte. De plus, les décalages utilisés par [ftell](../c-runtime-library/reference/ftell-ftelli64.md) et [fseek](../c-runtime-library/reference/fseek-fseeki64.md) comptent les octets depuis le début du flux (qui correspond à zéro octet) de sorte que l'arithmétique d'entiers sur ces décalages génère des résultats prévisibles.  
  
 Un flux d'octets traite un fichier comme une séquence d'octets. Dans le programme, le flux ressemble à la même séquence d'octets, à l'exception des modifications possibles décrites ci-dessus.  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers et flux](../c-runtime-library/files-and-streams.md)
