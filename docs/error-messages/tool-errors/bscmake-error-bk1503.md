---
title: "Erreur BSCMAKE BK1503 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1503"
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur BSCMAKE BK1503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'écrire dans le fichier 'nom\_fichier' \[: raison\]  
  
 BSCMAKE combine les fichiers .sbr générés au cours de la compilation en une seule base de données du navigateur.  Cette erreur est émise lorsque la taille de la base de données qui en résulte dépasse 64 Mo ou si le nombre de fichiers d'entrée \(.sbr\) est supérieur à 4 092.  
  
 Si le problème est causé par un nombre de fichiers .sbr supérieur à 4092, vous devez réduire le nombre de fichiers d'entrée.  Vous pouvez résoudre ce problème dans Visual Studio en appliquant l'option [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) à l'ensemble du projet, puis en revérifiant les fichiers un par un.  
  
 Si le problème est causé par un fichier .bsc de plus de 64 Mo, une réduction du nombre de fichiers .sbr en entrée se traduira par un fichier .bsc de plus petite taille.  De plus, la quantité d'informations de consultation peut être réduite à l'aide des options \/Em \(Exclure les symboles étendus par macro\), \/El \(Exclure les variables locales\) et \/Es \(Exclure les fichiers système\).  
  
## Voir aussi  
 [Options BSCMAKE](../../build/reference/bscmake-options.md)