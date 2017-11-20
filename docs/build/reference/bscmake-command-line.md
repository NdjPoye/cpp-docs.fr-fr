---
title: Ligne de commande BSCMAKE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 278518ae37a4e76ea4fe0252e3341e54daebe599
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-command-line"></a>Ligne de commande BSCMAKE
Pour exécuter BSCMAKE, utilisez la syntaxe de ligne de commande suivante :  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 Options peuvent apparaître uniquement dans le `options` de la ligne de commande.  
  
 Le *sbrfiles* champ spécifie un ou plusieurs fichiers .sbr créés par un compilateur ou un assembleur. Séparez les noms des fichiers .sbr par des espaces ou des tabulations. Vous devez spécifier l’extension. Il n’existe aucune valeur par défaut. Vous pouvez spécifier un chemin d’accès avec le nom de fichier, et vous pouvez utiliser des caractères génériques du système d’exploitation (* et ?).  
  
 Pendant une génération incrémentielle, vous pouvez spécifier de nouveaux fichiers .sbr qui ne faisaient pas partie de la génération d’origine. Si vous souhaitez que toutes les contributions de rester dans le fichier d’informations, vous devez spécifier tous les fichiers .sbr (y compris les fichiers tronqués) qui ont servi à créer le fichier .bsc. Si vous omettez un fichier .sbr, la contribution de ce fichier pour le fichier d’informations est supprimée.  
  
 Ne spécifiez pas un fichier .sbr tronqué pour une génération complète. Une génération complète nécessite la contribution de tous les fichiers .sbr spécifiés. Avant d’effectuer une génération complète, recompilez le projet et créer un nouveau fichier .sbr pour chaque fichier vide.  
  
 La commande suivante exécute BSCMAKE pour générer un fichier nommé MAIN.bsc à partir de trois fichiers .sbr :  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 Pour plus d’informations, consultez [BSCMAKE, fichier de commandes](../../build/reference/bscmake-command-file-response-file.md) et [Options BSCMAKE](../../build/reference/bscmake-options.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence BSCMAKE](../../build/reference/bscmake-reference.md)