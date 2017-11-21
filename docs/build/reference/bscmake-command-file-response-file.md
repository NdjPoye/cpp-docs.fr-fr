---
title: "BSCMAKE, fichier de commandes (fichier réponse) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1d5dd2696a48a84672350b90b569c8f0caf7c3cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE, fichier de commandes (fichier réponse)
Vous pouvez fournir tout ou partie de l’entrée de ligne de commande dans un fichier de commandes. Spécifiez le fichier de commandes à l’aide de la syntaxe suivante :  
  
```  
BSCMAKE @filename  
```  
  
 Fichier de commandes qu’un seul est autorisé. Vous pouvez spécifier un chemin d’accès avec *nom de fichier*. Faites précéder *nom de fichier* avec un arobase (@). BSCMAKE n’assume pas une extension. Vous pouvez spécifier supplémentaires *sbrfiles* sur la ligne de commande après *nom de fichier*. Le fichier de commandes est un fichier texte qui contient l’entrée à BSCMAKE dans le même ordre que vous devez la spécifier sur la ligne de commande. Séparez les arguments de ligne de commande avec un ou plusieurs espaces, tabulations ou caractères de saut de ligne.  
  
 La commande suivante appelle BSCMAKE en utilisant un fichier de commandes :  
  
```  
BSCMAKE @prog1.txt  
```  
  
 Voici un exemple de fichier de commandes :  
  
```  
/n /v /o main.bsc /El  
/S (  
toolbox.h  
verdate.h c:\src\inc\screen.h  
)  
file1.sbr file2.sbr file3.sbr file4.sbr  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence BSCMAKE](../../build/reference/bscmake-reference.md)