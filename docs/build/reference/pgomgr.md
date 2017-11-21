---
title: pgomgr | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ab078acd8aaadef19659ad766233ea191b360e02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="pgomgr"></a>pgomgr
Ajoute des données de profil à partir d’un ou plusieurs fichiers .pgc au fichier .pgd.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
pgomgr [options] pgcfiles pgdfile  
```  
  
#### <a name="parameters"></a>Paramètres  
 `options`  
 Les options suivantes peuvent être spécifiées à pgomgr :  
  
 **/help :**affiche les options disponibles pgomgr (abréviation de / ?).  
  
 **/Clear :**, le fichier .pgd à effacer toutes les informations de profil. Vous ne pouvez pas spécifier un .pgc fichier lorsque **/effacer** est spécifié.  
  
 **/Detail**— affiche des statistiques détaillées, y compris les informations de couverture du graphique de flux.  
  
 **/ summary**— affiche des statistiques par fonction.  
  
 **/unique**, lorsqu’il est utilisé avec **/summary**, entraîne affichage des noms de fonction l'décorés.  La valeur par défaut, lorsque est unique non utilisé, est pour les noms de fonction non décoré à afficher.  
  
 **/Merge**[**:***n*]**:**entraîne les données dans le fichier .pgc ou les fichiers à ajouter au fichier .pgd.  Le paramètre facultatif,  *n* , vous permet de spécifier hat les données doit être ajouté  *n*  fois.  Par exemple, si un scénario serait effectué couramment 6 fois, vous pouvez exécuter une fois dans une série de tests et ajoutez-la au fichier .pgd six fois avec **pgomgr/merge : 6**.  
  
 `pgcfiles`  
 Un ou plusieurs fichiers .pgc dont vous souhaitez fusionner dans le fichier .pgd les données de profil. Vous pouvez spécifier un fichier .pgc unique ou plusieurs fichiers .pgc. Si vous ne spécifiez pas de tous les fichiers .pgc, pgomgr fusionne tous les fichiers .pgc dont les noms de fichiers sont les mêmes que le fichier .pgd.  
  
 `pgdfile`  
 Le fichier .pgd dans lequel vous fusionnez des données à partir de l’ou les fichiers .pgc.  
  
## <a name="remarks"></a>Remarques  
  
> [!NOTE]
>  Vous pouvez démarrer cet outil uniquement à partir de l'invite de commandes [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. Vous ne pouvez pas le démarrer à partir d'une invite de commandes système ni de l'Explorateur de fichiers.  
  
## <a name="example"></a>Exemple  
 Dans l’exemple suivant, le fichier .pgd a été effacé des données de profil.  
  
```  
pgomgr /clear myapp.pgd  
```  
  
 Dans l’exemple suivant, les données de profil dans myapp1.pgc a été ajoutées au fichier .pgd 3 fois.  
  
```  
pgomgr /merge:3 myapp1.pgc myapp.pgd  
```  
  
 Dans l’exemple suivant, les données de profil à partir de tous les fichiers myapp # .pgc sont ajoutées au fichier myapp.pgd.  
  
```  
pgomgr -merge myapp1.pgd  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Outils de l’optimisation guidée par profil](../../build/reference/tools-for-manual-profile-guided-optimization.md)