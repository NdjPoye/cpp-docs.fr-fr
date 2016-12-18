---
title: "pgosweep | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pgosweep (programme)"
  - "optimisations guidées par profil, pgosweep"
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pgosweep
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé dans l'optimisation guidée par profil pour écrire toutes les données de profil d'un programme en cours d'exécution sur le fichier .pgc.  
  
## Syntaxe  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### Paramètres  
 `options`  
 Il n'est pas nécessaire de remplir un paramètre facultatif.  Les valeurs valides pour `options` sont les suivantes :  
  
-   **\/?** ou **\/help,** affiche le message d'aide.  
  
-   **\/noreset,**conserve le compte dans les structures de données d'exécution.  
  
 `image`  
 Chemin d'accès complet d'un fichier.exe ou .dll créé à l'aide de l'option du compilateur \/LTCG:PGINSTRUMENT.  
  
 `pgcfile`  
 Fichier .pgc dans lequel cette commande écrit les comptes de données.  
  
## Notes  
 Cette commande fonctionne sur les programmes créés avec l'option du compilateur \/LTCG:PGINSTRUMENT.  Elle interrompt un programme en cours d'exécution, puis écrit les données de profil sur un nouveau fichier .pgc.  Par défaut, la commande réinitialise les comptes après chaque opération d'écriture.  Si vous spécifiez l'option **\/noreset**, la commande enregistre les valeurs, mais ne les réinitialise pas dans le programme en cours d'exécution.  Cette option duplique les données si vous récupérez les données de profil ultérieurement.  
  
 `pgosweep` vous permet également de récupérer des informations de profil uniquement pour l'exécution de l'application.  Par exemple, vous pouvez exécuter `pgosweep` juste après avoir démarré l'application et ignorer ce fichier.  Cette opération vous permet de supprimer les données de profil associées aux coûts de démarrage.  Vous pouvez ensuite exécuter `pgosweep` avant de quitter l'application.  Les données recueillies ne possèdent désormais que des informations de profil créées lors des exécutions.  
  
 Lorsque vous nommez un fichier .pgc \(`pgcfile`\), vous pouvez utiliser le format standard, c'est\-à\-dire *appname\!n*.pgc.  Si vous utilisez ce format, le compilateur recherchera ces données dans la phase \/LTCG:PGO.  Si vous n'utilisez pas le format standard, vous devez utiliser [pgomgr](../../build/reference/pgomgr.md) pour fusionner les fichiers .pgc.  
  
## Exemple  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 Dans cet exemple, `pgosweep` écrit les informations de profil actuelles pour myapp.exe sur myapp\!1.pgc.  
  
## Voir aussi  
 [Outils de l'optimisation guidée par profil](../../build/reference/tools-for-manual-profile-guided-optimization.md)