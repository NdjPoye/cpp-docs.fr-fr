---
title: pgosweep | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c703bc68a36dd21c837e62738d9d2c2631502a0d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="pgosweep"></a>pgosweep
Utilisé dans l’optimisation guidée par profil pour écrire toutes les données de profil à partir d’un programme en cours d’exécution dans le fichier .pgc.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### <a name="parameters"></a>Paramètres  
 `options`  
 Un paramètre optionnel qui peut être vide. Les valeurs valides pour `options` sont les suivantes :  
  
-   **/?** ou **/help,** affiche le message d’aide.  
  
-   **/NoReset,** conserve le compte dans les structures de données de runtime.  
  
 `image`  
 Le chemin d’accès complet d’un fichier .exe ou .dll qui a été créé à l’aide de l’option/LTCG : PGINSTRUMENT du compilateur.  
  
 `pgcfile`  
 Le fichier .pgc où cette commande écrit les données de nombres.  
  
## <a name="remarks"></a>Remarques  
 Cette commande fonctionne sur les programmes qui ont été générés avec l’option de compilateur/LTCG : PGINSTRUMENT. Il interrompt un programme en cours d’exécution et écrit les données de profil dans un nouveau fichier .pgc. Par défaut, la commande réinitialise les comptes après chaque opération d’écriture. Si vous spécifiez la **/noreset** option, la commande enregistre les valeurs, mais pas Réinitialisez-les dans le programme en cours d’exécution. Cette option vous donnera de données en double si vous récupérez les données de profil ultérieurement.  
  
 Une utilisation alternative pour `pgosweep` consiste à récupérer les informations de profil uniquement pour l’exécution de l’application. Par exemple, vous pouvez exécuter `pgosweep` peu de temps après le démarrage de l’application et d’ignorer ce fichier. Cette action supprimera les données de profil associées à des coûts de démarrage. Vous pouvez ensuite exécuter `pgosweep` avant la fin de l’application. Les données collectées ont maintenant des informations de profil uniquement à partir de l’exécution.  
  
 Lorsque vous nommez un fichier .pgc (`pgcfile`) vous pouvez utiliser le format standard, qui est *appname ! n*.pgc. Si vous utilisez ce format, le compilateur recherche ces données dans la phase / LTCG : PGO. Si vous n’utilisez pas le format standard, vous devez utiliser [pgomgr](../../build/reference/pgomgr.md) pour fusionner les fichiers .pgc.  
  
## <a name="example"></a>Exemple  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 Dans cet exemple, `pgosweep` écrit les informations de profil actuelles pour myapp.exe sur myapp ! 1.pgc.  
  
## <a name="see-also"></a>Voir aussi  
 [Outils de l’optimisation guidée par profil](../../build/reference/tools-for-manual-profile-guided-optimization.md)