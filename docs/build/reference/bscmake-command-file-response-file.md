---
title: "BSCMAKE, fichier de commandes (fichier réponse) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c250af9f1af96bb051be0b2cd347ecd8d98d809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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