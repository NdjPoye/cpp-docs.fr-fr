---
title: E/S de bas niveau | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- I/O [CRT], low-level
- I/O [CRT], functions
- low-level I/O routines
- file handles [C++]
- file handles [C++], I/O functions
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
caps.latest.revision: 9
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
ms.openlocfilehash: 36128b5f262ef84986c2a4e0db1b7eeceee14ec3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="low-level-io"></a>E/S niveau bas
Ces fonctions appellent le système d’exploitation directement pour l’opération du niveau inférieur à celui fourni par les E/S de flux. Les appels de bas niveau et de sortie ne mettent pas les données en mémoire tampon et ne les formatent pas.  
  
 Les routines de bas niveau peuvent accéder aux flux standard ouverts au démarrage du programme à l’aide des descripteurs de fichier prédéfinis suivants.  
  
|Flux de données|Descripteur de fichier|  
|------------|---------------------|  
|`stdin`|0|  
|`stdout`|1|  
|`stderr`|2|  
  
 Les routines d’E/S de bas niveau définissent la variable globale [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) lorsqu’une erreur se produit. Vous devez inclure STDIO.H lorsque vous utilisez des fonctions de bas niveau uniquement si votre programme requiert une constante définie dans STDIO.H, comme l’indicateur de fin de fichier (`EOF`).  
  
### <a name="low-level-io-functions"></a>Fonctions d’E/S de bas niveau  
  
|Fonction|Utilisation|  
|--------------|---------|  
|[_close](../c-runtime-library/reference/close.md)|Fermer le fichier|  
|[_commit](../c-runtime-library/reference/commit.md)|Vider le fichier sur disque|  
|[_creat, _wcreat](../c-runtime-library/reference/creat-wcreat.md)|Créer le fichier|  
|[_dup](../c-runtime-library/reference/dup-dup2.md)|Retourne le descripteur de fichier disponible suivant pour le fichier donné|  
|[_dup2](../c-runtime-library/reference/dup-dup2.md)|Créer le deuxième descripteur pour le fichier donné|  
|[_eof](../c-runtime-library/reference/eof.md)|Vérifier la fin du fichier|  
|[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|Repositionner le pointeur de fichier vers un emplacement donné|  
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Ouvrir un fichier|  
|[_read](../c-runtime-library/reference/read.md)|Lire des données depuis le fichier|  
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Ouvrir le fichier pour le partage de fichiers|  
|[_tell, _telli64](../c-runtime-library/reference/tell-telli64.md)|Obtenir la position actuelle du pointeur de fichier|  
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Définir le masque file-permission|  
|[_write](../c-runtime-library/reference/write.md)|Écrire les données dans le fichier|  
  
 `_dup` et `_dup2` servent généralement à associer les descripteurs de fichier prédéfinis à différents fichiers.  
  
## <a name="see-also"></a>Voir aussi  
 [Entrée et sortie](../c-runtime-library/input-and-output.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Appels système](../c-runtime-library/system-calls.md)
