---
title: "pgomgr | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "pgomgr (programme)"
  - "optimisations guidées par profil, pgomgr"
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pgomgr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute les données de profil d'un ou plusieurs fichiers .pgc au fichier .pgd.  
  
## Syntaxe  
  
```  
pgomgr [options] pgcfiles pgdfile  
```  
  
#### Paramètres  
 `options`  
 Les options suivantes peuvent être spécifiées à pgomgr :  
  
 **\/help** : affiche les options pgomgr disponibles \(abréviation de \/?\).  
  
 **\/clear** : entraîne l'effacement de toutes les informations de profil contenues dans le fichier .pgd.  Vous ne pouvez pas définir de fichier .pgc lorsque **\/clear** est spécifié.  
  
 **\/detail** : affiche des statistiques détaillées, notamment des informations sur la couverture du graphe de flux.  
  
 **\/summary** : affiche des statistiques fonction par fonction.  
  
 **\/unique** : en cas d'utilisation avec **\/summary**, entraîne l'affichage des noms de fonctions décorés.  La valeur par défaut, lorsque \/unique n'est pas utilisé, est l'affichage des noms de fonctions non décorés.  
  
 **\/merge**\[**:***n*\] : entraîne l'ajout au fichier .pgd des données contenues dans le ou les fichiers .pgc.  Le paramètre facultatif, *n*, vous permet de spécifier que les données doivent être ajoutées *n* fois.  Par exemple, si un scénario est habituellement exécuté 6 fois, vous pouvez l'exécuter une fois lors d'une série de tests et l'ajouter six fois au fichier .pgd à l'aide de **pgomgr\/merge:6**.  
  
 `pgcfiles`  
 Un ou plusieurs fichiers .pgc dont vous souhaitez fusionner les données de profil dans le fichier .pgd.  Vous pouvez spécifier un fichier .pgc unique ou plusieurs fichiers .pgc.  Si vous ne spécifiez pas de fichier .pgc, pgomgr fusionne tous les fichiers .pgc dont le nom de fichier est identique à celui du fichier .pgd.  
  
 `pgdfile`  
 Le fichier .pgd dans lequel vous fusionnez les données du ou des fichiers .pgc.  
  
## Notes  
  
> [!NOTE]
>  Vous pouvez démarrer cet outil uniquement à partir de l'invite de commandes [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  Vous ne pouvez pas le démarrer à partir d'une invite de commandes système ou dans l'Explorateur Windows.  
  
## Exemple  
 Dans l'exemple suivant, les données de profil ont été effacées du fichier .pgd.  
  
```  
pgomgr /clear myapp.pgd  
```  
  
 Dans l'exemple suivant, les données de profil contenues dans myapp1.pgc ont été ajoutées 3 fois au fichier .pgd.  
  
```  
pgomgr /merge:3 myapp1.pgc myapp.pgd  
```  
  
 Dans l'exemple suivant, les données de profil de tous les fichiers myapp\#.pgc sont ajoutées au fichier myapp.pgd.  
  
```  
pgomgr -merge myapp1.pgd  
```  
  
## Voir aussi  
 [Outils de l'optimisation guidée par profil](../../build/reference/tools-for-manual-profile-guided-optimization.md)