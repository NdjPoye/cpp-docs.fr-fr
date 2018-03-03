---
title: Erreur BSCMAKE BK1503 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK1503
dev_langs:
- C++
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 86f2b6d282857409cdb1e1d49e04775e9886cde4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1503"></a>Erreur BSCMAKE BK1503
Impossible d’écrire dans le fichier 'nom_fichier' [ : raison]  
  
 BSCMAKE combine les fichiers .sbr générés pendant la compilation dans une base de données du navigateur. Si la base de données du navigateur qui en résulte dépasse 64 Mo, ou si le nombre de fichiers d’entrée (.sbr) est supérieur à 4092, cette erreur est émise.  
  
 Si le problème est causé par des fichiers .sbr supérieur à 4092, vous devez réduire le nombre de fichiers d’entrée. À partir de Visual Studio, cela peut être accompli par [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) votre ensemble du projet, puis revérifier chaque fichier par fichier.  
  
 Si le problème est provoqué par un fichier .bsc supérieur à 64 Mo, ce qui réduit le nombre de fichiers .sbr en tant qu’entrée diminue la taille du fichier .bsc obtenu. En outre, la quantité d’informations de consultation peut être réduite via l’utilisation de la /Em (exclure les symboles de développé de Macro), /El (exclure les Variables locales) et /Es (exclure les fichiers de système).  
  
## <a name="see-also"></a>Voir aussi  
 [Options BSCMAKE](../../build/reference/bscmake-options.md)